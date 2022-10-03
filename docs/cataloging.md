# Cataloging
## Cataloging workflows
### Adding
1. Add items to existing records
2. Add new record via Z39.50 if no record exists, then add item
3. Request record from SEKLS if no record exists via Z39.50
### Deleting
1. Delete item
2. Delete record if no other items are attached
## Adding items
### Searching
#### Basic search
- Start with a keyword search on ISBN if available.
    **Don’t give up after one search**, try different combinations of terms and filters.
    Using multiple terms in the keyword search like _Title_ and _Author_ or _Title_ and _Actor_ can get more refined results.
#### Advanced search
- Click **Search** in the top navigation menu to access the Advanced search for a more exact search involving multiple indexes:
   
> ***Reminders***
> - Check spelling and punctuation
> - You can keyword search on title and author, or title and actor at the same time
> - Try variations 
>     - Season one = season 1 = first season = 1st season
>     - Sorcerers = sorcerer’s
> - You can scan various barcodes like UPCs and ISBNs to avoid entry errors
> - Additional search tips are available in the <a href="https://docs.google.com/document/d/1kypYylxi9GYCUyD9yFhLvQsXW-DPXE3dufCfhkoA2fQ/edit#bookmark=id.5gyeca5r7br">Circulation documentation</a>

### Matching
- Review the search results to determine if the item in hand matches an existing record.
- Check for:
    1. Title
	2. Author
	3. Publication information
	4. Paging/size/format
	5. ISBN
    6. Copyright date

### Adding the item
1. Click **New** then **New item**.
2. Fill in the **required** fields then click **Add item**.
	
## Editing items
1. Click into the record detail view and find your item in the holds table.
2. Click **Edit** in the far right column for the item you wish to update.
3. Make any adjustments, then click **Save changes**.

## Deleting items
### Delete single item
1. From the record detail view, click the **checkbox** next to your item.
2. Click **Delete selected items**.
3. Click **Delete selected items** on the next screen.

### Delete multiple items
1. Click **More** > **Tools** > **Batch item deletion**
2. Scan your pile of books into the **barcode list box** then click **Continue**
3. Click **Delete selected items**.
	
## Adding records
### Using Z39.50 Targets
#### Search
- When your search turns up empty, click the **Z39.50/SRU search** button.
- Enter info into the search form - start with just ISBN and try other approaches and additional terms.

> ***Search tips***
> - Add actors in the <strong>Author </strong> field
> - Add <em>videodisc </em>or <em>dvd </em>or <em>videorecording </em> to the keyword field for movies
> - Add <em>sound recording </em>or <em>sound disc </em>or <em>disc </em> to the keyword field for audiobooks
> - Checking additional targets can provide more results (but may slow down the search)
> - UPCs and other codes can be entered in the <strong>Keyword (any)</strong> field

#### Choose the best record
1. Click **Card preview** for a quick look at the record quality
2. Evaluate the quality of the record. Click the **X** to return to the search results.
3. Click **Import** for the chosen record.

#### Edit & save
1. Click the **9** tab and add a Koha item type to the **942$c** field.
2. Add any missing relevant info including paging, dimensions, series info, etc.
3. Click **Save**, then add your item.

> ***Avoid duplicates***
> - If you see a yellow box, click the <strong>title</strong> to see if the record you are adding duplicates the existing record

### Using MARC files
1. Obtain a MARC file from an external source (SHAREit, vendor, etc.)
2. In Koha, go to **More** > **Tools** > **Stage MARC records for import**.
3. Browse to the file on your computer then click **Upload file**.
4. **Default** settings should be sufficient for most situations. Adjust rules if necessary.
5. Click **Stage for import**.
6. Click **Manage staged records**.
7. Click **Import this batch into the catalog**.
8. Review the results – click on the **Record number** to quickly get to the new or matched record.

## Editing records
### Getting there
1. Search for and click into the record detail view.
2. Click on **Edit** > **Edit record**.
3. Locate the field needing adjustment using the numbered tabs along the top.
4. Click **Save** when finished.

### Duplicating and deleting fields
1. Duplicate field
2. Delete field
3. Duplicate subfield
4. Delete subfield

### Field editors
- Some fields have extra helpers for entering data. Click this symbol to the right of the entry box for a new window with additional guidance.

## Deleting records
- To delete an empty record, pull up the record detail view then click **Edit** > **Delete record**.
    - _Note: Empty records are deleted at the time of item deletion in most cases._

## Advanced cataloging
### Separating combo packs
If only a combo pack record is available, import the record then duplicate it.
  - **Blu-ray records** should have these values in the appropriate fields:
<table>
  <tr>
   <td><strong>Field</strong>
   </td>
   <td><strong>Subfield/position</strong>
   </td>
   <td><strong>Used for</strong>
   </td>
   <td><strong>Value</strong>
   </td>
  </tr>
  <tr>
   <td>007
   </td>
   <td>position 04
   </td>
   <td>Encoding
   </td>
   <td>s
   </td>
  </tr>
  <tr>
   <td>250
   </td>
   <td>a
   </td>
   <td>Edition
   </td>
   <td>Blu-ray edition
   </td>
  </tr>
  <tr>
   <td>300
   </td>
   <td>a
   </td>
   <td>Description - Extent
   </td>
   <td>1 Blu-ray videodisc (120 minutes) :
   </td>
  </tr>
  <tr>
   <td>538
   </td>
   <td>a
   </td>
   <td>System description note
   </td>
   <td>Blu-ray disc; requires Blu-ray player.
   </td>
  </tr>
  <tr>
   <td colspan="4" ><em>Any other occurrences of DVD should be changed to Blu-ray. Check other 3XX, 5XX, and 6XX fields.</em>
   </td>
  </tr>
</table>

  - **DVD records** should have these values in the appropriate fields:
<table>
  <tr>
   <td><strong>Field</strong>
   </td>
   <td><strong>Subfield/position</strong>
   </td>
   <td><strong>Used for</strong>
   </td>
   <td><strong>Value</strong>
   </td>
  </tr>
  <tr>
   <td>007
   </td>
   <td>position 04
   </td>
   <td>Encoding
   </td>
   <td>v
   </td>
  </tr>
  <tr>
   <td>250
   </td>
   <td>a
   </td>
   <td>Edition
   </td>
   <td>[remove]
   </td>
  </tr>
  <tr>
   <td>300
   </td>
   <td>a
   </td>
   <td>Description - Extent
   </td>
   <td>1 videodisc (120 minutes) :
   </td>
  </tr>
  <tr>
   <td>538
   </td>
   <td>a
   </td>
   <td>System description note
   </td>
   <td>DVD…
   </td>
  </tr>
  <tr>
   <td colspan="4" ><em>Any other occurrences of Blu-ray should be changed to DVD. Check other 3XX, 5XX, and 6XX fields.</em>
   </td>
  </tr>
</table>

## Cleanup
1. Click **Quick links** then **Clean-up reports**.
2. Click on **Cataloging** and click **Run**.
3. Fix any issues – a blank report means no issues exist.

## MARC reference
### Frequently used fields and subfields
<table>
  <tr>
   <td>Field
   </td>
   <td>Subfield(s)
   </td>
   <td>What’s it for?
   </td>
   <td>Which records need it?
   </td>
  </tr>
  <tr>
   <td>020
   </td>
   <td>a
   </td>
   <td>ISBN
   </td>
   <td>Most
   </td>
  </tr>
  <tr>
   <td>100
   </td>
   <td>a
   </td>
   <td>Author
   </td>
   <td>Most
   </td>
  </tr>
  <tr>
   <td>245
   </td>
   <td>a, b
   </td>
   <td>Title, subtitle
   </td>
   <td>All
   </td>
  </tr>
  <tr>
   <td>246
   </td>
   <td>a
   </td>
   <td>Other title
   </td>
   <td>Some
   </td>
  </tr>
  <tr>
   <td>250
   </td>
   <td>a
   </td>
   <td>Edition statement
   </td>
   <td>Some
   </td>
  </tr>
  <tr>
   <td>260 or 264
   </td>
   <td>a, b, c
   </td>
   <td>Publisher info
   </td>
   <td>All
   </td>
  </tr>
  <tr>
   <td>300
   </td>
   <td>a, b, c
   </td>
   <td>Paging, size, etc.
   </td>
   <td>All
   </td>
  </tr>
  <tr>
   <td>336, 337, 338
   </td>
   <td> 
   </td>
   <td>RDA identifiers
   </td>
   <td>Most
   </td>
  </tr>
  <tr>
   <td>440/490
   </td>
   <td>a, v
   </td>
   <td>Series info
   </td>
   <td>Some
   </td>
  </tr>
  <tr>
   <td>5XX
   </td>
   <td> 
   </td>
   <td>Notes
   </td>
   <td>Some
   </td>
  </tr>
  <tr>
   <td>6XX
   </td>
   <td> 
   </td>
   <td>Subjects
   </td>
   <td>Most
   </td>
  </tr>
  <tr>
   <td>7XX
   </td>
   <td> 
   </td>
   <td>Additional authors, actors, illustrator, etc.
   </td>
   <td>Some
   </td>
  </tr>
  <tr>
   <td>942
   </td>
   <td>c
   </td>
   <td>Item type
   </td>
   <td>All
   </td>
  </tr>
  <tr>
   <td>942
   </td>
   <td>n
   </td>
   <td>OPAC suppression
   </td>
   <td>Some
   </td>
  </tr>
</table>

### Series resources
<table>
  <tr>
   <td>
    <strong>KDL What’s Next</strong>
   </td>
   <td>
    <a href="http://ww2.kdl.org/libcat/whatsnext.asp">http://ww2.kdl.org/libcat/whatsnext.asp</a>
   </td>
  </tr>
  <tr>
   <td>
    <strong>Goodreads Series Search</strong>
   </td>
   <td>
    <a href="https://cse.google.com/cse/home?cx=002960089167042347160:8rxwxouel4i&hl=en">https://cse.google.com/cse/home?cx=002960089167042347160:8rxwxouel4i&hl=en</a>
   </td>
  </tr>
  <tr>
   <td>
    <strong>MCPL Juvenile Series</strong>
   </td>
   <td>
    <a href="https://www.mymcpl.org/books-movies-music/read/juvenile-series-and-sequels">https://www.mymcpl.org/books-movies-music/read/juvenile-series-and-sequels</a>
   </td>
  </tr>
  <tr>
   <td>
    <strong>Fantastic Fiction</strong>
   </td>
   <td>
    <a href="https://www.fantasticfiction.com/">https://www.fantasticfiction.com/</a>
   </td>
  </tr>
  <tr>
   <td>
    <strong>Order of Books</strong>
   </td>
   <td>
    <a href="https://www.orderofbooks.com/">https://www.orderofbooks.com/</a>
   </td>
  </tr>
  <tr>
   <td>
    <strong>Amazon </strong>
   </td>
   <td>
    <a href="https://www.amazon.com/">https://www.amazon.com/</a>
   </td>
  </tr>
</table>

## Cataloging by format
### Book

<table>
  <tr>
   <td><strong><span style="text-decoration:underline;">Tag</span></strong>
   </td>
   <td><strong><span style="text-decoration:underline;">Contains</span></strong>
   </td>
   <td><strong><span style="text-decoration:underline;">Sample values</span></strong>
   </td>
  </tr>
  <tr>
   <td>000
   </td>
   <td>Leader
   </td>
   <td><strong>a </strong>in pos 6, <strong>Full level</strong> in pos 17, <strong>i</strong> in pos 18
   </td>
  </tr>
  <tr>
   <td>020a
   </td>
   <td>ISBN
   </td>
   <td><strong>9781400226979</strong>
   </td>
  </tr>
  <tr>
   <td>040e
   </td>
   <td>Description conventions
   </td>
   <td><strong>rda</strong>
   </td>
  </tr>
  <tr>
   <td>100a
   </td>
   <td>Author
   </td>
   <td><strong>Goff, Bob,</strong>
   </td>
  </tr>
  <tr>
   <td>245a
   </td>
   <td>Title
   </td>
   <td><strong>Undistracted :</strong>
   </td>
  </tr>
  <tr>
   <td>246a
   </td>
   <td>Other title
   </td>
   <td><strong>Un distracted</strong>
   </td>
  </tr>
  <tr>
   <td>250a
   </td>
   <td>Edition statement
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>264a
   </td>
   <td>Publisher - place
   </td>
   <td>Nashville, TN :
   </td>
  </tr>
  <tr>
   <td>264b
   </td>
   <td>Publisher - name
   </td>
   <td>Nelson Books, an imprint of Thomas Nelson,
   </td>
  </tr>
  <tr>
   <td>264c
   </td>
   <td>Publisher - date
   </td>
   <td>[2022].
   </td>
  </tr>
  <tr>
   <td>300a
   </td>
   <td>Description - extent (paging)
   </td>
   <td>vii, 221 pages ;
   </td>
  </tr>
  <tr>
   <td>300c
   </td>
   <td>Description - dimensions (size)
   </td>
   <td>24 cm.
   </td>
  </tr>
  <tr>
   <td>336
   </td>
   <td>Content type
   </td>
   <td>text
   </td>
  </tr>
  <tr>
   <td>337
   </td>
   <td>Media type
   </td>
   <td>unmediated
   </td>
  </tr>
  <tr>
   <td>338
   </td>
   <td>Carrier type
   </td>
   <td>volume
   </td>
  </tr>
  <tr>
   <td>490a
   </td>
   <td>Series - title
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>490v
   </td>
   <td>Series - book number
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>500+
   </td>
   <td>Note fields
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>600+
   </td>
   <td>Subject headings
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>700+
   </td>
   <td>Additional authors
   </td>
   <td>
   </td>
  </tr>
</table>

