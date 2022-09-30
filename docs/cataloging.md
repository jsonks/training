## Workflow

![alt text](assets/cat_workflow.png)

## Searching

### Finding an existing record
Start your search with the **Search the catalog** tab of the main search bard.
![alt text](assets/cat_search1.png)

Keyword searches scan the entire record; start with a **Keyword** search on **ISBN**.
![alt text](assets/cat_search2.png)

*Don't give up after one search!* Try different search terms and filters.
Title & Author
![alt text](assets/cat_search3.png)
Title with the *Title* filter selected
![alt text](assets/cat_search4.png)
Use *Advanced search* for a Title & Author or Title & Actor search
![alt text](assets/cat_search5.png)
	
> #### SEKnFind search tips
> - Check spelling and punctuation
> - Try variations:
> 	- season 1 = season one = first season
> 	- sorcerer's = sorcerers = sorcerer s
> - Try fewer words in long titles
> - Add articles (a, an, the) for shorter titles
> - Use author/actor names with short titles
> - Use common keywords like DVD, Blu-ray, videodisc, sound recording

## Matching
The item your cataloging must match the record you're adding it to.
![alt text](assets/cat_match1.png)

When comparing results to the item in hand, pay attention to:
> 1. Title
> 2. Author
> 3. Publisher
> 4. Paging / Size / Number of discs
> 5. ISBNs
> 6. Copyright date
![alt text](assets/cat_match2.png)

## Adding items
When you find a record that matches your item, add your item.

1. Click **New** then **New item**
![alt text](assets/cat_add1.png)
2. Fill in the required fields
![alt text](assets/cat_add2.png)
3. Click **Add item**

## Adding records
When you are unable to find a record that matches your item, you should attempt to find a record via Z39.50. If no records are available there, contact the SEKLS cataloging department for assistance.

### Z39.50 record import
1. From the search results screen, click **Z39.50/SRU search**
![alt text](assets/cat_z39import1.png)
2. In the window that pops up, enter your search term(s)
![alt text](assets/cat_z39import2.png)
	> #### Z39.50 search tips
	> - Try ISBN alone
	> - Try Title + Author/Actor
	> - Try UPCs and other numbers in the 'Keyword' or 'Standard ID' fields
	> - Add *videodisc* or *dvd* or *videorecording* or *blu* in the keyword field for movies
	> - Pre-checked targets are faster, but you can also try unchecked targets for more results
	> - Check your spelling and punctuation
3. Pick the best record.
	- Review title, author, publication date, ISBN and description.
	- You can click the **Card** link for more details, and **MARC** for full details.
	![alt text](assets/cat_z39import3.png)
4. Import the chosen record by clicking **Import**
![alt text](assets/cat_z39import4.png)
5. Add an itemtype in the **942$c** -- the record won't save without one.
![alt text](assets/cat_z39import5.png)

> #### Avoid duplicates
> ![alt text](assets/cat_z39import6.png)
> If you see this box appear, make sure the existing record won't work for your item by click on the linked title.
>
> If the record matches, add your item to it. If not, return to the yellow box and choose **No, save as new record**.

### Adding records from SHAREit

#### Grab records from SHAREit
1. Log in to SHAREit.
![alt text](assets/cat_shareit1.png)
2. Create a list.
![alt text](assets/cat_shareit2.png)
3. Search and add records to the list.
![alt text](assets/cat_shareit3.png)
4. Download the list.
![alt text](assets/cat_shareit4.png)

#### Upload records to Koha
1. Click **More**, **Tools**, **Stage MARC records for import**
![alt text](assets/cat_marcimport1.png)
2. Browse to your .mrc file or drag it from your downloads folder to the browse button
![alt text](assets/cat_marcimport2.png)
3. Click **Upload**
4. Match these settings
![alt text](assets/cat_marcimport3.png)
5. Click **Stage for import**

#### Import records
1. Click **Manage staged records** button.
![alt text](assets/cat_marcimport4.png)
2. Click **Import this batch into the catalog** button.
![alt text](assets/cat_marcimport5.png)
3. Wait.
![alt text](assets/cat_marcimport6.png)
4. A completion message and links to your new records will appear once the import is complete.
![alt text](assets/cat_marcimport7.png)

## MARC reference
Most records will use these fields and subfields:
|    Field            |    Subfield(s)    |    What’s it for?                                   |    Which records need it?    |
|---------------------|-------------------|-----------------------------------------------------|------------------------------|
|    020              |    a              |    ISBN                                             |    Most                      |
|    100              |    a              |    Author                                           |    Most                      |
|    245              |    a, b           |    Title, subtitle                                  |    All                       |
|    246              |    a              |    Other title                                      |    Some                      |
|    250              |    a              |    Edition statement                                |    Some                      |
|    260 or 264       |    a, b, c        |    Publisher info                                   |    All                       |
|    300              |    a, b, c        |    Paging, size, etc.                               |    All                       |
|    336, 337, 338    |                   |    RDA identifiers                                  |    Most                      |
|    440/490          |    a, v           |    Series info                                      |    Some                      |
|    5XX              |                   |    Notes                                            |    Some                      |
|    6XX              |                   |    Subjects                                         |    Most                      |
|    7XX              |                   |    Additional authors, actors, illustrator, etc.    |    Some                      |
|    942              |    c              |    Item type                                        |    All                       |
|    942              |    n              |    OPAC suppression                                 |    Some                      |

Example record:
|    Field            |    Subfield    |    Used for                                         |    Example                    |
|---------------------|----------------|-----------------------------------------------------|-------------------------------|
|    000 (Leader)     |    pos 06      |    Encodes item format                              |    a                          |
|    000 (Leader)     |    pos 18      |    Encodes cataloging type                          |    i for RDA, a for AACR2     |
|    020              |    a           |    ISBN                                             |    0399157336                 |
|    100              |    a           |    Author                                           |    Coulter, Catherine         |
|    245              |    a           |    Title                                            |    Bombshell /                |
|    246              |    a           |    Other title                                      |    Bomb shell                 |
|    250              |    a           |    Edition statement                                |    1st edition.               |
|    264              |    a           |    Publisher - Place                                |    New York :                 |
|    264              |    b           |    Publisher - Name                                 |    G.P. Putnam's Sons         |
|    264              |    c           |    Publisher - Date                                 |    2013.                      |
|    300              |    a           |    Description - Extent                             |    392 pages ;                |
|    300              |    c           |    Description - Dimensions                         |    24 cm.                     |
|    336, 337, 338    |                |    RDA identifiers                                  |                               |
|    490              |    a           |    Series - Title                                   |    FBI series ;               |
|    490              |    v           |    Series - Volume                                  |    bk. 17                     |
|    5XX              |                |    Notes                                            |                               |
|    6XX              |                |    Subjects                                         |    Murder -- Investigation    |
|    7XX              |                |    Additional authors, actors, illustrator, etc.    |    Coulter, Allen             |
|    942              |    c           |    Item type                                        |    Book                       |

## Deleting

### Deleting single items
1. Click **Edit** then **Edit items**
![alt text](assets/cat_delete1.png)
2. Find your item in the table, click **Actions** then **Delete**
![alt text](assets/cat_delete2.png)

### Deleting multiple items
1. Click **More**, **Tools**, **Batch item deletion**
![alt text](assets/cat_delete3.png)
2. Scan the barcode of each item into the **barcode list** box, then click **Continue**
![alt text](assets/cat_delete4.png)
3. **Uncheck** any items you wish to keep
![alt text](assets/cat_delete5.png)
4. Click **Delete selected items**.
![alt text](assets/cat_delete6.png)

### Deleting empty records
1. Click **Edit**, then **Delete record**
![alt text](assets/cat_delete7.png)
2. Click **OK**
![alt text](assets/cat_delete8.png)


