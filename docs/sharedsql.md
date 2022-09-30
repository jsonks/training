---
id: sharedsql
title: Shared Reports
sidebar_label: Shared SQL
---
## Acquisitions

### Newest items added in a ccode
Finds the most recent items added to a specific collection code within the past year


```
SELECT b.title, b.author, b.biblionumber, b.datecreated, i.barcode, i.dateaccessioned
FROM biblio b
LEFT JOIN items i USING (biblionumber)
WHERE i.homebranch = <<Select Library|branches>>
	AND i.ccode = <<Collection Code|CCODE>>
	AND i.dateaccessioned > DATE_SUB(CURDATE(),INTERVAL 1 YEAR)
ORDER BY i.dateaccessioned DESC
```

### Items added in a shelf location within a date range
Count of acquisitions in a selected yeah by shelf location

```
SELECT authorised_values.lib AS 'Shelving Location', COUNT(1) AS Count
FROM items
LEFT JOIN authorised_values ON (items.location=authorised_values.authorised_value)
WHERE items.homebranch = <<Library|branches>>
	AND items.dateaccessioned BETWEEN <<Start date|date>> AND <<End date|date>>
GROUP BY items.location
LIMIT 100
```

### Items added to a shelf location within a specified year, summarized by month
Lists out items added each month for the specified year in the specified shelf location

```
SELECT YEAR(items.dateaccessioned) as year, MONTHNAME(items.dateaccessioned) as month,
	concat(biblio.title, ' ', ExtractValue((
	SELECT marcxml 
	FROM biblioitems
	WHERE biblio.biblionumber = biblioitems.biblionumber),'//datafield[@tag="245"]/subfield[@code="b"]')) AS FullTitle,
biblio.author, items.itemcallnumber, items.ccode, count(*) as quantity
FROM biblio, items 
WHERE biblio.biblionumber = items.biblionumber 
	AND YEAR(items.dateaccessioned) = << Enter the year to select (yyyy) >>
	AND items.homebranch = <<Select your library|branches>>  
	AND items.location = <<Shelf Location|LOC>>
GROUP BY  month, FullTitle, items.itemcallnumber
ORDER BY MONTH(items.dateaccessioned), biblio.title
```

## Administration

### Authorized values list
Lists all authorized values and their descriptions

```
SELECT authorised_value, id, category, lib
FROM authorised_values
ORDER BY category
```

### Patrons with permissions
Lists patrons who have staff permissions

```
SELECT borrowers.cardnumber, borrowers.surname, borrowers.firstname, borrowers.branchcode, borrowers.categorycode,
borrowers.flags as 'permissions'
FROM borrowers
WHERE borrowers.branchcode = <<Select your library|branches>> 
	AND borrowers.flags > 0
ORDER BY borrowers.surname asc
```

## Catalog

### Contents of an Item Type
Lists ALL items in an item type

```
SELECT  items.barcode, items.homebranch, items.location, items.itype, items.ccode, biblio.title, biblio.author 
FROM items 
LEFT JOIN biblioitems on (items.biblioitemnumber=biblioitems.biblioitemnumber) 
LEFT JOIN biblio on (biblioitems.biblionumber=biblio.biblionumber)   
WHERE items.itype = <<Item Type|itemtypes>>
```

### Contents of a Shelf Location
Lists ALL items in a shelf location

```
SELECT  items.barcode, items.homebranch, items.holdingbranch, items.location, items.ccode, items.itype,
items.itemcallnumber, biblioitems.itemtype, biblio.author, biblio.title, items.itemlost,
ExtractValue(marcxml,'//datafield[@tag="300"]/subfield[@code>="a"]') AS Description
FROM items
LEFT JOIN biblioitems on (items.biblioitemnumber=biblioitems.biblioitemnumber)
LEFT JOIN biblio on (biblioitems.biblionumber=biblio.biblionumber)
WHERE items.location=<<Select Shelf Location|LOC>>
```

### Item count by Item Type
Counts how many items are in each iType at selected library

```
SELECT itemtypes.description AS 'Item Type', COUNT(1) AS Count
FROM items
LEFT JOIN itemtypes ON (items.itype=itemtypes.itemtype)
WHERE items.homebranch = <<Choose Library|branches>>
GROUP BY itemtypes.description
UNION ALL
SELECT 'TOTAL' itype, COUNT(1)
FROM items
WHERE homebranch = <<Choose Library|branches>>
```

### Item count by shelf location + item type
Counts how many items are each combination of shelf location and item type at a library

```
SELECT av.lib AS 'Shelving Location', it.description AS 'Item Type', COUNT(1) as Count
FROM items i
LEFT JOIN authorised_values av ON (i.location=av.authorised_value)
LEFT JOIN itemtypes it ON (i.itype=it.itemtype)
WHERE i.homebranch=<<Choose your library|branches>>
GROUP BY i.itype,i.location
ORDER BY it.description, av.lib ASC
```

### Lost report with links
Modified Items Lost report with links to the record detail and moredetail pages

```
SELECT av.lib AS 'Shelving Location', it.description AS 'Item Type', COUNT(1) as Count
FROM items i
LEFT JOIN authorised_values av ON (i.location=av.authorised_value)
LEFT JOIN itemtypes it ON (i.itype=it.itemtype)
WHERE i.homebranch=<<Choose your library|branches>>
GROUP BY i.itype,i.location
ORDER BY it.description, av.lib ASC
```
## Circulation

### Average circs each hour
Averages how many circulations occured each hour in a date range at a specific library. Can be used to locate your busiest times of day in terms of checkouts.

```
SELECT date_format(`datetime`,'%H') as 'Hour', count(*) as 'Checkouts and Renews' 
FROM statistics
WHERE datetime BETWEEN <<Starting date|date>> AND <<Ending date|date>>
	AND branch=<<Choose your library|branches>>
	AND type in ('issue','renew')
GROUP BY date_format(`datetime`,'%H')
```

### Titles with holds
Gives a complete list of bibs with holds including the title, number of holds, and number of items associated with each bib.

```
SELECT biblio.biblionumber, biblio.title, biblio.author, authorised_values.lib as collection,
count(DISTINCT reserves.borrowernumber) as reservecount, count(DISTINCT items.itemnumber) as itemcount
FROM reserves
LEFT JOIN items ON items.biblionumber=reserves.biblionumber 
LEFT JOIN biblio ON reserves.biblionumber=biblio.biblionumber
LEFT JOIN authorised_values ON items.ccode=authorised_values.authorised_value
GROUP BY reserves.biblionumber
ORDER BY reservecount DESC
```

### Top 10 circulating items in a Shelf Location
Reports the 10 most circulated items in a shelf location in a date range.

```
SELECT count(o.issuedate) AS circs,
CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',title,'</a>') AS Title, b.author
FROM old_issues o
LEFT JOIN items i ON (i.itemnumber=o.itemnumber) 
LEFT JOIN biblio b ON (b.biblionumber=i.biblionumber) 
WHERE DATE(o.issuedate) > <<Range start date|date>> 
	AND DATE(o.issuedate) <= <<Range end date|date>> 
	AND i.homebranch = <<Library|branches>>
	AND i.location = <<Shelf location|LOC>>
	AND o.itemnumber IS NOT NULL
GROUP BY b.biblionumber
ORDER BY circs DESC 
LIMIT 10
```

## Collection Analysis

### Age stats from call# range
Shows the average age of the books in a call range based on publication dates. Useful for weeding and collection development.

```
SELECT AVG(copyrightdate)
FROM biblio
LEFT JOIN items ON biblio.biblionumber=items.biblionumber 
WHERE items.itemcallnumber BETWEEN <<starting call number>> AND <<ending call number>>
	AND items.homebranch LIKE <<Select Library|branches>>
	AND biblio.copyrightdate IS NOT NULL
```

### Subject search
Finds all items added within a date range with a specific subject.


```
SELECT *
FROM(SELECT
    items.dateaccessioned,
    items.barcode,
    items.itemcallnumber,
    biblio.title,
    biblio.author,
    biblioitems.isbn,
    (SELECT ExtractValue(biblio_metadata.metadata,'//datafield[@tag="650"]/subfield[@code>="a"]'))  AS Subject, items.homebranch AS Branch
     FROM items
     LEFT JOIN biblioitems ON(items.biblioitemnumber=biblioitems.biblioitemnumber)
     LEFT JOIN biblio ON (biblioitems.biblionumber=biblio.biblionumber)
     LEFT JOIN biblio_metadata ON (items.biblionumber=biblio_metadata.biblionumber)
     WHERE items.dateaccessioned BETWEEN '2017-05-01' AND '2019-06-01') AS t
WHERE  Subject LIKE concat('%','Christian Fiction','%') AND Branch LIKE 'IOLA'
ORDER BY dateaccessioned DESC
```

## Consortial Stats

### Items added in a year
Count of items added at each library in a selected year based on acquisition date (migration libraries will be inaccurate)

```
SELECT homebranch, COUNT(*)
FROM items
WHERE YEAR(dateaccessioned) = <<Year>>
AND (ccode <> 'PER' AND ccode <> 'ILL' AND ccode <> 'ROT' OR ccode IS NULL)
GROUP BY i.homebranch
ORDER BY i.homebranch
LIMIT 150
```

### Items deleted in a year
Count of items deleted at each library in a selected year, years prior to migration will be inaccurate

```
SELECT homebranch, COUNT(*)
FROM deleteditems
WHERE YEAR(timestamp)=<<Year (YYYY)>>
GROUP BY homebranch
ORDER BY homebranch
LIMIT 150
```

### Total number of items at each library
Shows item count at each branch

```
SELECT homebranch,count(*) as items 
FROM items 
GROUP BY homebranch 
ORDER BY homebranch asc 
LIMIT 150
```

### Total bib count
Number of records in the entire collection

```
SELECT COUNT(1) as Records
FROM biblio
```

### Total item count
Number of itms in the entire collection

```
SELECT COUNT(1) as Items
FROM items
```

## Database clean-up

### Bad cataloging
Runs comparisons on various authorized values to locate miscataloged items

```
SELECT i.barcode, b.title, i.ccode, a.lib, i.homebranch, i.dateaccessioned, i.booksellerid AS Whodunnit
FROM items i
LEFT JOIN biblio b ON i.biblionumber=b.biblionumber
LEFT JOIN authorised_values a ON i.location=a.authorised_value
WHERE (i.location NOT LIKE '%STORED%'
	AND i.location NOT LIKE '%ILL%'
	AND i.location NOT LIKE '%NEW%'
	AND i.location NOT LIKE '%BKDISCUSS%'
	AND i.location NOT LIKE '%OFFICE%'
	AND i.location NOT LIKE '%KSHC%'
	AND i.location NOT LIKE '%COMPUSE%'
	AND i.location NOT LIKE '%DISPLAY%'
	AND i.location NOT LIKE '%ERYBODY%'
	AND i.location NOT LIKE '%LEASED%'
	AND i.location NOT LIKE '%SRAREA%'
	AND i.location NOT LIKE '%GAMEPUZ%')
AND ((i.ccode LIKE 'AB' AND i.location NOT BETWEEN '100100ADFICCF' AND '121800YAREF') 
	OR (i.ccode LIKE 'AUD' AND i.location NOT LIKE '%AUD%')
	OR (i.ccode LIKE 'BLU' AND i.location NOT LIKE '%BLU%')
	OR (i.ccode LIKE 'DEF')
	OR (i.ccode LIKE 'DVD' AND i.location NOT LIKE '%DVD%')
	OR (i.ccode LIKE 'ER' AND i.location NOT LIKE '%ER%')
	OR (i.ccode LIKE 'GAM' AND i.location NOT LIKE '%SOF%')
	OR (i.ccode LIKE 'ILL' AND i.location NOT LIKE '%ILL%')
	OR (i.ccode LIKE 'JB' AND i.location NOT BETWEEN '140100JUVFICBR' AND '160400JUVNFILL')
	OR (i.ccode LIKE 'MIC' AND i.location NOT LIKE '%MICRO%')
	OR (i.ccode LIKE 'MUS' AND i.location NOT LIKE '%AUDM%')
	OR (i.ccode LIKE 'PER' AND i.location NOT LIKE '%MAG%')
	OR (i.ccode LIKE 'SOF' AND i.location NOT LIKE '%SOF%')
	OR (i.ccode LIKE 'STT')
	OR (i.ccode LIKE 'VHS' AND i.location NOT LIKE '%VHS%')
	OR (i.ccode LIKE 'XXX'))
ORDER BY a.lib
```

### Bibs added in a time frame
Pulls all bibs created within a selected window of time

```
SELECT b.biblionumber, b.title, b.author,
ExtractValue(marcxml,'//datafield[@tag="300"]/subfield[@code>="a"]') AS Description,  b.datecreated, b.timestamp
FROM biblioitems bi
LEFT JOIN biblio b on (bi.biblionumber=b.biblionumber) 
WHERE b.datecreated BETWEEN <<Between|date>> AND <<and|date>> 
ORDER BY b.datecreated ASC
```

### Bibs with duplicate ISBNs
Finds cases where multiple records have the same ISBN and links to a search for them. Used to find records to merge.
```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/search.pl?q=',isbn,'\" target="_blank">',isbn,'</a>') AS 'ISBN Search',
COUNT(*) AS 'No. of Matching Records'
FROM biblioitems
GROUP BY isbn
HAVING COUNT(*) > 1
```

### Bibs with many items
Finds bibs with more than X amount of items. Useful for finding records that are bogged down, esp. periodicals.

```
SELECT biblio.biblionumber, title, author, count(*)
FROM items, biblio
WHERE biblio.biblionumber=items.biblionumber
GROUP BY biblio.biblionumber having count(*) > <<Find bibs with more than XXX items>>
ORDER BY count(*) DESC
```

### Deleted items for specific bib
Useful for re-adding items that accidentally get deleted

```
SELECT *
FROM deleteditems
LEFT JOIN biblio USING (biblionumber)
WHERE biblionumber = <<Enter Bib Number>>
```

### Empty bibs
Bibs without items attached

```
SELECT biblionumber, title, datecreated 
FROM biblio 
WHERE biblionumber NOT IN (SELECT biblionumber FROM items)
```

### Items without replacement prices filtered on shelf location
Pulls any legacy data from the 541 field to help populate missing item information

```
SELECT i.barcode, i.itemcallnumber, b.author, b.title, i.replacementprice,
ExtractValue(bi.marcxml, "//datafield[@tag='541']/subfield[@code='a']" ) AS 'Source',
ExtractValue(bi.marcxml, "//datafield[@tag='541']/subfield[@code='d']" ) AS 'Date',
ExtractValue(bi.marcxml, "//datafield[@tag='541']/subfield[@code='f']" ) AS 'Owner',
ExtractValue(bi.marcxml, "//datafield[@tag='541']/subfield[@code='h']" ) AS 'Purchase Price'
FROM items i
LEFT JOIN biblio b ON (i.biblionumber=b.biblionumber)
LEFT JOIN biblioitems bi ON (i.biblionumber=bi.biblionumber)
WHERE i.homebranch = <<Library|branches>>
	AND i.location = <<Shelf Location|LOC>>
	AND i.ccode <> 'ILL'
	AND i.ccode <> 'ROT'
	AND i.replacementprice IS NULL
ORDER BY i.itemcallnumber
```

### Items with missing data
Identifies items without collection code (ccode), item type (itype), shelf location (shelving loc), call number, or barcode. 
```
SELECT CONCAT('<a target="_blank" href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',biblio.biblionumber,'&itemnumber=',items.itemnumber,'\">','Edit item','</a>') AS link,
    items.dateaccessioned,
    items.itemcallnumber,
    a.lib as shelfLoc,
    items.ccode,
    items.itype,
    CONCAT('<a target="_blank" href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',biblio.biblionumber,'\">',title,'</a>') AS Title,
    biblio.author,
    items.barcode
FROM items
LEFT JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber)
LEFT JOIN biblio ON (biblioitems.biblionumber=biblio.biblionumber)
LEFT JOIN authorised_values a ON (items.location=a.authorised_value)
WHERE (items.location IS NULL
       OR items.ccode IS NULL
       OR items.itype IS NULL
       OR items.barcode IS NULL
       OR items.itemcallnumber IS NULL)
  AND items.homebranch <> 'DOWNLOAD'
  AND items.itype <> 'ILL'
  AND items.homebranch LIKE 'IOLA'
ORDER BY items.dateaccessioned DESC
```
Add this style declaration to the notes field to highlight blank fields in yellow:

```
<style>
#report_results table tbody tr td:nth-child(3):empty, #report_results table tbody tr td:nth-child(4):empty, #report_results table tbody tr td:nth-child(5):empty, #report_results table tbody tr td:nth-child(6):empty, #report_results table tbody tr td:nth-child(9):empty {
	background-color: lightgoldenrodyellow !important;
}
</style>
```

## Inventory

### Items not scanned in a shelf location during inventory
Lists items not scanned within a shelf location during inventory. Excludes items that are in transit, checked out, or waiting on hold. Used to identify and search for items that aren't where they should be.
```
SELECT
     i.itemcallnumber, b.title, b.author, i.barcode, datelastseen, a.lib AS 'lost', a2.lib AS 'notloan', a3.lib AS 'withdrawn', a4.lib AS 'damaged',
     IF(MAX(bt.datesent)>COALESCE(MAX(bt.datearrived),0),'Yes','No') as inTransit, i.holdingbranch
 FROM biblio b
 LEFT JOIN items i USING (biblionumber)
 LEFT JOIN reserves r USING (itemnumber)
 LEFT JOIN authorised_values a ON (a.authorised_value=i.itemlost AND a.category='LOST')
 LEFT JOIN authorised_values a2 ON (a2.authorised_value=i.notforloan AND a2.category='NOT_LOAN')
 LEFT JOIN authorised_values a3 ON (a3.authorised_value=i.withdrawn AND a3.category='WITHDRAWN')
 LEFT JOIN authorised_values a4 ON (a4.authorised_value=i.withdrawn AND a4.category='DAMAGED')
 LEFT JOIN branchtransfers bt ON (i.itemnumber = bt.itemnumber)
 WHERE datelastseen < <<Date you started inventory/Date last seen before|date>> 
                 AND i.homebranch = <<Choose Library|branches>>
                 AND i.location=<<Location|LOC>>
                 AND i.onloan IS NULL
                 AND r.waitingdate IS NULL
                 AND r.found IS NULL
GROUP BY i.itemnumber
HAVING inTransit = 'No'
ORDER BY i.itemcallnumber, b.author, b.title
```

### Items not scanned during inventory
Lists ALL items not scanned. Useful for batching a list of items into a lost status.
```
SELECT
     i.itemcallnumber, b.title, b.author, i.barcode, datelastseen, a.lib AS 'lost', a2.lib AS 'notloan', a3.lib AS 'withdrawn', a4.lib AS 'damaged',
     IF(MAX(bt.datesent)>COALESCE(MAX(bt.datearrived),0),'Yes','No') as inTransit, i.holdingbranch
 FROM biblio b
 LEFT JOIN items i USING (biblionumber)
 LEFT JOIN reserves r USING (itemnumber)
 LEFT JOIN authorised_values a ON (a.authorised_value=i.itemlost AND a.category='LOST')
 LEFT JOIN authorised_values a2 ON (a2.authorised_value=i.notforloan AND a2.category='NOT_LOAN')
 LEFT JOIN authorised_values a3 ON (a3.authorised_value=i.withdrawn AND a3.category='WITHDRAWN')
 LEFT JOIN authorised_values a4 ON (a4.authorised_value=i.withdrawn AND a4.category='DAMAGED')
 LEFT JOIN branchtransfers bt ON (i.itemnumber = bt.itemnumber)
 WHERE datelastseen < <<Date you started inventory/Date last seen before|date>> 
                 AND i.homebranch = <<Choose Library|branches>>
                 AND i.onloan IS NULL
                 AND r.waitingdate IS NULL
                 AND r.found IS NULL
GROUP BY i.itemnumber
HAVING inTransit = 'No'
ORDER BY i.itemcallnumber, b.author, b.title
```

## Monthly

### Long overdues AT other libraries
Overdue items that are owned by your library, but checked out elsewhere.
```
SELECT items.barcode, biblio.title, items.itemcallnumber, items.homebranch AS "Owned by", issues.date_due,
items.holdingbranch AS "Checked out at" 
FROM items 
LEFT JOIN  biblio on(items.biblionumber=biblio.biblionumber) 
LEFT JOIN  issues on(items.itemnumber=issues.itemnumber) 
LEFT JOIN  borrowers on(issues.borrowernumber=borrowers.borrowernumber) 
WHERE  items.homebranch = <<Choose Library|branches>>
	AND  items.holdingbranch != <<Choose Library|branches>>
	AND  issues.date_due != ' '
	AND  issues.date_due is not NULL 
	AND  issues.date_due < DATE_SUB(curdate(), INTERVAL '99' DAY)  
ORDER BY  items.holdingbranch
```

### Long overdues FROM other libraries
Overdue items that are owned by someone else, but checked out at your library.

```
SELECT borrowers.cardnumber,  borrowers.firstname,  borrowers.surname,  borrowers.phone,  borrowers.email, items.barcode,
biblio.title, items.itemcallnumber, items.homebranch AS "Owned by", issues.date_due, items.holdingbranch AS "Checked out at" 
FROM items 
LEFT JOIN  biblio on(items.biblionumber=biblio.biblionumber) 
LEFT JOIN  issues on(items.itemnumber=issues.itemnumber) 
LEFT JOIN  borrowers on(issues.borrowernumber=borrowers.borrowernumber) 
WHERE  items.homebranch != <<Choose Library|branches>>
	AND  items.holdingbranch = <<Choose Library|branches>>
	AND  items.homebranch <> 'ROTATION'
	AND  issues.date_due !=  
	AND  issues.date_due is not NULL 
	AND  issues.date_due < DATE_SUB(curdate(), INTERVAL '99' DAY)  
ORDER BY  items.homebranch
```

### Transfers FROM your library
Transfers being sent from your library that have not arrived yet

```
SELECT b.datesent, b.frombranch, b.tobranch, items.homebranch, items.barcode, biblio.title, biblio.author,
items.itemcallnumber, DATEDIFF(b.datesent, (DATE_SUB(curdate(), INTERVAL 5 day)) ) * -1 as dayslate
FROM branchtransfers as b
LEFT JOIN items on (b.itemnumber = items.itemnumber)
LEFT JOIN biblioitems on (biblioitems.biblioitemnumber = items.biblioitemnumber)
LEFT JOIN biblio on (biblio.biblionumber = biblioitems.biblionumber)
WHERE b.frombranch = <<Select your library|branches>>
	AND b.datearrived is NULL
	AND items.homebranch <> 'ROTATION'
	AND DATEDIFF(b.datesent, (DATE_SUB(curdate(), INTERVAL 5 day)) ) * -1 > '0'
ORDER BY dayslate DESC
```

## Year-end

### Yearly circulation stats by collection code
Gives total checkouts + renewals in a year, broken down by ccode, with a grand total at the end.

```
SELECT a.lib AS 'Collection Code', COUNT(1) AS 'Circs'
FROM statistics s
LEFT JOIN items i ON s.itemnumber=i.itemnumber
LEFT JOIN authorised_values a ON i.ccode=a.authorised_value
WHERE YEAR(s.datetime) = <<Enter year (YYYY)>>
	AND s.branch = <<Choose Library|branches>>
	AND s.type IN ('issue', 'renew')
GROUP BY a.lib
UNION ALL
SELECT 'TOTAL' ccode, COUNT(1) AS 'Circs'
FROM statistics
WHERE YEAR(datetime) = <<Enter Year(YYYY)>>
	AND branch = <<Choose Library|branches>>
	AND type IN ('issue', 'renew')
```

### Item count by collection code
Gives total number of items in each collection code with a grand total at the end.
```
SELECT authorised_values.lib AS 'Collection Code', COUNT(1) AS Count
FROM items
LEFT JOIN authorised_values ON (items.ccode=authorised_values.authorised_value)
WHERE items.homebranch = <<Choose Library|branches>>
GROUP BY items.ccode
UNION ALL
SELECT 'TOTAL' ccode, COUNT(1)
FROM items
WHERE homebranch = <<Choose Library|branches>>
```

### Item count by shelf location
Gives total number of items in each shelf location with a grand total at the end.
```
SELECT authorised_values.lib AS 'Shelving Location', COUNT(1) AS Count
FROM items
LEFT JOIN authorised_values ON (items.location=authorised_values.authorised_value)
WHERE items.homebranch = <<Choose Library|branches>>
GROUP BY items.location
UNION ALL
SELECT 'TOTAL' location, COUNT(1)
FROM items
WHERE homebranch = <<Choose Library|branches>>
LIMIT 100
```

### Circulation of Juv/YA materials in given year
Sums circs for each shelf location with a grand total at the end.
```
SELECT COALESCE(a.lib, 'TOTAL') AS 'Shelf Location',  COUNT(*) AS 'Circs' 
FROM statistics s
LEFT JOIN items i ON (s.itemnumber=i.itemnumber)
LEFT JOIN authorised_values a ON (i.location=a.authorised_value)
WHERE 1=1  
	AND YEAR(s.datetime) = <<Year (YYYY)>>
	AND s.branch LIKE <<Home branch|branches>>
	AND s.type IN ('issue', 'renew')
	AND (i.location LIKE '%YA%'  OR  i.location LIKE '%JUV%')
GROUP BY a.lib
WITH ROLLUP
LIMIT 50
```