## Parameters

Parameters allow users to make choices about what info the report retrieves.

Parameter formatting: `<<Descriptive text|parameter>>`

Vanilla Koha parameters:

* Library/Branch: branches
* Shelf Location: LOC
* Item Type: itemtypes
* Collection Code: CCODE
* Lost Status: LOST
* Not for Loan Status: NOT_LOAN
* Withdrawn Status: WITHDRAWN
* Damaged Status: DAMAGED
* Patron Category: categorycode
* Pop-up Calendar: date
* Any authorized value category can be used as a parameter.

An authorized value of % creates a wildcard which can be used as an 'ALL' search. Wildcards must be queried with `LIKE <<parameter>>` instead of `= <<parameter>>`.

## Recipes

### SELECT Statement Links

#### View Bib Record

```sql
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',biblio.biblionumber,'\" target="_blank">'"View"'</a>') AS "view"
```

#### Edit Item Record

```sql
SELECT CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',biblio.biblionumber,'&itemnumber=',items.itemnumber,'\" target="_blank" >',"Edit",'</a>') AS "edit"
```

#### View Patron Account

```sql
SELECT CONCAT('<a href=\"/cgi-bin/koha/circ/circulation.pl?borrowernumber=',borrowers.borrowernumber,'\" target="_blank">',"View Account",'</a>') AS "view"
```
#### Edit Patron Account

```sql
SELECT CONCAT('<a href=\"/cgi-bin/koha/members/memberentry.pl?op=modify&borrowernumber=',borrowers.borrowernumber,'\" target="_blank">',"Edit",'</a>') AS "edit"
```
#### View Account Permissions

```sql
SELECT CONCAT('<a href=\"/cgi-bin/koha/members/member-flags.pl?member=',borrowers.borrowernumber,'\" target="_blank">',"Edit",'</a>') AS "link"
```

### Coalescence
`COALESCE` can be used to fill in gaps from like tables. This is helpful when querying existing and deleted data simultaneously.

#### Query collection codes from items & deleted items

```sql
SELECT COALESCE(items.ccode, deleteditems.ccode) AS 'collection code'
```
### Date range picker
Useful for filtering reports within a specific time frame.

```sql
WHERE date_due BETWEEN <<Between|date>> AND <<and|date>>
```

### Recolor clicked links within a report
Adding styles to the notes field, and a class within the SELECT statement link can help distinguish between links that have and haven't been clicked within a report. This is useful on clean-up reports where the links open in new tabs. You can click the link, then close the tab and not lose your place within the report.

#### Add the style to the report notes field

```html
<style>
.clicked:visited {
     color:hotpink;
 }
 </style>
```

#### Add a class to the link
```sql
SELECT CONCAT('<a class="clicked" target="_blank" href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',biblio.biblionumber,'&itemnumber=',items.itemnumber,'\" >',"Edit",'</a>') AS "edit"
```

### Sum Case When
Useful for categorizing multiple locations/ccodes/itypes together. For example, we have multiple YA shelf locations in two different AV ranges.

```sql
SELECT SUM(CASE WHEN (i.location BETWEEN '101800YAFIC' AND '102100YAFICSF')
	OR (i.location BETWEEN '121600YANFB' AND '121800YAREF') THEN 1 ELSE 0 END) as 'Young Adult Books'
FROM items i
```

### In Transit check
Checks whether the item is in transit and reports a 'yes' or 'no'.

```sql
SELECT IF(MAX(bt.datesent)>COALESCE(MAX(bt.datearrived),0),'Yes','No') as inTransit
FROM branchtransfers bt
```

### Multiple Authorised Value joins
Allows for cleaner reports by pulling descriptions rather than raw codes for different categories.

```sql
SELECT
     a.lib AS 'lost',
     a2.lib AS 'notloan',
     a3.lib AS 'withdrawn',
     a4.lib AS 'damaged',
 FROM items i
 LEFT JOIN authorised_values a ON (a.authorised_value=i.itemlost AND a.category='LOST')
 LEFT JOIN authorised_values a2 ON (a2.authorised_value=i.notforloan AND a2.category='NOT_LOAN')
 LEFT JOIN authorised_values a3 ON (a3.authorised_value=i.withdrawn AND a3.category='WITHDRAWN')
 LEFT JOIN authorised_values a4 ON (a4.authorised_value=i.damaged AND a4.category='DAMAGED')
```
