---
id: additemhelper
title: Item Cataloging Helper
sidebar_label: Item Cataloging Helper
---
This project streamlines the addition of items by rearranging the 'Add Item' fields into a more logical order and prefilling collection code when a shelf location is selected.
## Sorted Fields
![additemhelper](assets/addItemHelper1.png)

## Helper in Action
![additemhelper](assets/addItemHelper2.gif)


## JS

### Add classes
This makes it easier to manipulate each field.
* Fields that will be used and moved around are given unique classes.
* Fields that will not be used are given the "hidden" class.
* Fields that are required are given the "required" class (this is to create the illusion that the fields are required -- to enforce a requirement you can set it up in the MARC framework).

```js
//Classes
$('#cat_additem span:contains("Withdrawn status")').parent().parent().parent().addClass('withdrawn');
$('#cat_additem span:contains("Lost status")').parent().parent().parent().addClass('lost');
$('#cat_additem span:contains("Not for loan")').parent().parent().parent().addClass('notloan');
$('#cat_additem span:contains("Permanent location")').parent().parent().parent().addClass('homebranch');
$('#cat_additem span:contains("Current location")').parent().parent().parent().addClass('holdingbranch');
$('#cat_additem span:contains("Shelving location")').parent().parent().parent().addClass('shelfloc');
$('#cat_additem span:contains("Collection code")').parent().parent().parent().addClass('ccode');
$('#cat_additem span:contains("Full call number")').parent().parent().parent().addClass('callnumber');
$('#cat_additem span:contains("Barcode")').parent().parent().parent().addClass('bcode');
$('#cat_additem span:contains("Copy number")').parent().parent().parent().addClass('copy');
$('#cat_additem span:contains("Koha item type")').parent().parent().parent().addClass('itype');
$('#cat_additem span:contains("Date acquired")').parent().parent().parent().addClass('accessiondate');
$('#cat_additem span:contains("Source of acquisition")').parent().parent().parent().addClass('source');
$('#cat_additem span:contains("Cost, normal purchase price")').parent().parent().parent().addClass('purchase');
$('#cat_additem span:contains("Cost, replacement price")').parent().parent().parent().addClass('replacement');
$('#cat_additem span:contains("Non-public note")').parent().parent().parent().addClass('nonpublic');
$('#cat_additem span:contains("Public note")').parent().parent().parent().addClass('public');

//Hidden
$('#cat_additem span:contains("Source of classification or shelving scheme")').parent().parent().parent().addClass('hidden'); 
$('#cat_additem span:contains("Materials specified (bound volume or other part)")').parent().parent().parent().addClass('hidden');
$('#cat_additem span:contains("Damaged status")').parent().parent().parent().addClass('hidden'); 
$('#cat_additem span:contains("Use restrictions")').parent().parent().parent().addClass('hidden'); 
$('#cat_additem span:contains("Inventory number")').parent().parent().parent().addClass('hidden');
$('#cat_additem span:contains("Shelving control number")').parent().parent().parent().addClass('hidden'); 
$('#cat_additem span:contains("Coded location qualifier")').parent().parent().parent().addClass('hidden');
$('#cat_additem span:contains("Uniform Resource Identifier")').parent().parent().parent().addClass('hidden');
$('#cat_additem span:contains("Price effective from")').parent().parent().parent().addClass('hidden');

//Required fields
$('#cat_additem .accessiondate label').addClass('required');
$('#cat_additem .source label').addClass('required');
$('#cat_additem .purchase label').addClass('required');
$('#cat_additem .replacement label').addClass('required');
$('#cat_additem .shelfloc label').addClass('required');
$('#cat_additem .ccode label').addClass('required');
$('#cat_additem .callnumber label').addClass('required');
$('#cat_additem .bcode label').addClass('required');
$('#cat_additem .itype label').addClass('required');
```

### Add headings
Inserts headings before certain fields to help better organize fields on the page.
```js
//Headings
$('#cat_additem span:contains("Withdrawn status")').parent().parent().parent().prepend('<h4 class="cathead">Statuses</h4><hr>');
$('#cat_additem span:contains("Permanent location")').parent().parent().parent().prepend('<h4>Location</h4><hr>');
$('#cat_additem span:contains("Date acquired")').parent().parent().parent().prepend('<h4>Acquisition</h4><hr>');
$('#cat_additem span:contains("Shelving location")').parent().parent().parent().prepend('<h4>Classification</h4><hr>');
$('#cat_additem span:contains("Non-public note")').parent().parent().parent().prepend('<h4>Notes</h4><hr>');
```

### Rearrange the fields
Move the unhidden fields under the appropriate headings/
```js
//Move
$('#cat_additem .ccode').insertAfter('#cat_additem .shelfloc'); //ccode
$('#cat_additem .public').insertAfter('#cat_additem .nonpublic'); //notes
$('#cat_additem .accessiondate').insertAfter('#cat_additem .holdingbranch'); //date acquired
$('#cat_additem .source').insertAfter('#cat_additem .accessiondate'); //source
$('#cat_additem .purchase').insertAfter('#cat_additem .source'); //cost
$('#cat_additem .replacement').insertAfter('#cat_additem .purchase'); //cost
$('#cat_additem .itype').insertAfter('#cat_additem .copy'); //itemtype
```

### The helper function
The helper function associates shelf locations with collection codes, then populates the collection code depending on the location selected. The helper also toggles the 'Serial Enumeration' field so it only shows if a location in the 'Magazine' array is selected.

```js
function catHelper(val) {
    var adultbook = ['100100ADFICCF', '100200ADFIC', '100250ADFICGN', '100300ADFICHF', '100400ADFICM', '100450ADFICHOL', '100500ADFICPBK', '100600ADFICPBKM', '100700ADFICPBKSF', '100800ADFICPBKW', '100850ADFICR', '100900ADFICSF', '101000ADFICW', '101100KFIC', '101200LPFICCF', '101300LPFIC', '101400LPFICM', '101500LPFICSF', '101600LPFICW', '101700ADFICILL', '101800YAFIC', '101900YAFICGN', '102000YAFICPBKF', '102100YAFICSF', '120100ADNFB', '120200ADNF', '120300ADNFREF', '120400ADNFTC', '120450AUTO', '120600KDNF', '120700KNF', '120800KRNF', '120900LPNFB', '121000LPNF', '121200ADNFQ', '121300ADNFPC', '121400ADNFILL', '121600YANFB', '121700YANF', '121800YAREF', '130300SRAREA', '130400ADSPANISH', '340225KSHC']
    var audiobook = ['260100ADAUDCAS', '260200ADAUDCD', '260250ADAUDMP3', '260300ADAUDPL', '260430ADAUDCDPC', '260460ADAUDCDILL', '260500YAAUDCAS', '260600YAAUDCD', '260700YAAUDPL', '280100JUVAUDBAC', '280200JUVAUDCAS', '280300JUVAUDCD', '280400JUVAUDPL']
    var bluray = ['220100ADVIDBLU', '240100JUVVIDBLU']
    var device = ['240300JUVVIDPL', '320400EREADER', '320440ADLPAD', '320450JUVLPAD']
    var dvd = ['220200ADVIDDVD', '220500ADVIDDVDPC', '220600ADVIDDVDILL', '240200JUVVIDDVD']
    var game = ['300150SOFPS', '300200SOFPS2', '300300SOFPS3', '300310SOFPS4', '300370SOF3DS', '300380SOFSWITCH', '300400SOFWII', '300410SOFWIIU', '300500SOFXBOX360', '300500SOFXBOXONE', '320250BGAMEPUZ']
    var juvbook = ['130450JUVSPANISH', '140100JUVFICBR', '140200JUVFICBB', '140300JUVFICBRA', '140325JUVFICBC', '140350JUVFICCHI', '140400JUVFICE', '140450JUVFICP', '140500JUVFIC', '140600JUVFICGN', '140700JUVFICHOL', '140800JUVFICLP', '140950JUVFICILL', '160100JUVNFB', '160150JUVNFBRA', '160175JUVNFHOL', '160200JUVNF', '160300JUVNFREF', '160400JUVNFILL', '170100ERYBODY']
    var microform = ['320700MICROFILM']
    var music = ['260400ADAUDMUS', '280500JUVAUDMUS']
    var periodical = ['180100ADMAG', '200100JUVMAG', '180200YAMAG']
    var rota = ['340200ROTA']
    var software = ['300050SOFCOMPPC', '300100SOFCOMP']
    var specialCollections = ['121500ADNFVF', '130100ECH', '130250NBC', '130500WMINGE', '140900JUVFICPAT', '320100ARTPRINT', '320200BAKING', '320300EQUIPMENT', '320500KITS', '320700PASS', '320800PHOTO', '320950PCKIT', '340205ARCHIVE', '340300SPECNEED']
    var stats = ['380100COMPUSE']
    var vhs = ['220400ADVIDVHS', '240400JUVVIDVHS']

    //Adult Books
    if ($.inArray(val, adultbook) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('AB').change();

    //Audiobooks
    } else if ($.inArray(val, audiobook) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('AUD').change();

    //Blu-rays
    } else if ($.inArray(val, bluray) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('BLU').change();

    //Devices
    } else if ($.inArray(val, device) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('DEV').change();

    //DVDs
    } else if ($.inArray(val, dvd) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('DVD').change();

    //Games
    } else if ($.inArray(val, game) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('GAM').change();

    //Juvenile Books
    } else if ($.inArray(val, juvbook) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('JB').change();

    //Microform
    } else if ($.inArray(val, microform) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('MIC').change();

    //Music
    } else if ($.inArray(val, music) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('MUS').change();

    //Periodicals
    } else if ($.inArray(val, periodical) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().show(500);
        $('[id*="tag_952_subfield_8_"]').val('PER').change();

    //Rotation
    } else if ($.inArray(val, rota) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('ROT').change();

    //Software
    } else if ($.inArray(val, software) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('SOF').change();

    //Special Collections
    } else if ($.inArray(val, specialCollections) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('SPC').change();

    //Stats
    } else if ($.inArray(val, stats) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('STT').change();

    //VHS
    } else if ($.inArray(val, vhs) !== -1) {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
        $('[id*="tag_952_subfield_8_"]').val('VHS').change();

    //Everything Else
    } else {
        $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
    }
}
```

### Call the helper function
Whenever a shelf location is chosen, the function triggers and chooses the appropriate collection code.
```js
//Change ccode based on shelfloc
$("[id*='tag_952_subfield_c_']").on('change', function() {
    var selected = $(this).val();
    catHelper(selected);
});
```

### Show the 'Serial Enumeration' field when duping an item
Clunky workaround to show the 'Serial Enumeration' field when duplicating an existing item.
```js
//Serial enumeration
if (window.location.href.indexOf("dupeitem") === -1) { //show field if dupe button is used
    $('#cat_additem span:contains("Serial Enumeration / chronology")').parent().parent().parent().addClass('serial').hide(); 
}
```

## CSS

### Format the fake 'required' notation
Colors the text red and adds an asterisk.
```css
#cataloguing_additem_newitem fieldset.rows label.required:after {
    color: red;
    content: " *";
}
```
### Align text labels to the right
This makes it easier to see which field goes with which label.
```css
#cataloguing_additem_newitem fieldset.rows label, #cataloguing_additem_newitem fieldset.rows span.label {
	width: 25%;
	text-align: right !important;
}
```

## Complete Code:

### IntranetUserJS
```js
//Item Cataloging Helper
$(document).ready(function() {

    //Classes
    $('#cat_additem span:contains("Withdrawn status")').parent().parent().parent().addClass('withdrawn');
    $('#cat_additem span:contains("Lost status")').parent().parent().parent().addClass('lost');
    $('#cat_additem span:contains("Not for loan")').parent().parent().parent().addClass('notloan');
    $('#cat_additem span:contains("Permanent location")').parent().parent().parent().addClass('homebranch');
    $('#cat_additem span:contains("Current location")').parent().parent().parent().addClass('holdingbranch');
    $('#cat_additem span:contains("Shelving location")').parent().parent().parent().addClass('shelfloc');
    $('#cat_additem span:contains("Collection code")').parent().parent().parent().addClass('ccode');
    $('#cat_additem span:contains("Full call number")').parent().parent().parent().addClass('callnumber');
    $('#cat_additem span:contains("Barcode")').parent().parent().parent().addClass('bcode');
    $('#cat_additem span:contains("Copy number")').parent().parent().parent().addClass('copy');
    $('#cat_additem span:contains("Koha item type")').parent().parent().parent().addClass('itype');
    $('#cat_additem span:contains("Date acquired")').parent().parent().parent().addClass('accessiondate');
    $('#cat_additem span:contains("Source of acquisition")').parent().parent().parent().addClass('source');
    $('#cat_additem span:contains("Cost, normal purchase price")').parent().parent().parent().addClass('purchase');
    $('#cat_additem span:contains("Cost, replacement price")').parent().parent().parent().addClass('replacement');
    $('#cat_additem span:contains("Non-public note")').parent().parent().parent().addClass('nonpublic');
    $('#cat_additem span:contains("Public note")').parent().parent().parent().addClass('public');

    //Serial enumeration
    if (window.location.href.indexOf("dupeitem") === -1) { //show field if dupe button is used
    $('#cat_additem span:contains("Serial Enumeration / chronology")').parent().parent().parent().addClass('serial').hide(); 
    }

    //Hide
    $('#cat_additem span:contains("Source of classification or shelving scheme")').parent().parent().parent().addClass('hidden'); 
    $('#cat_additem span:contains("Materials specified (bound volume or other part)")').parent().parent().parent().addClass('hidden');
    $('#cat_additem span:contains("Damaged status")').parent().parent().parent().addClass('hidden'); 
    $('#cat_additem span:contains("Use restrictions")').parent().parent().parent().addClass('hidden'); 
    $('#cat_additem span:contains("Inventory number")').parent().parent().parent().addClass('hidden');
    $('#cat_additem span:contains("Shelving control number")').parent().parent().parent().addClass('hidden'); 
    $('#cat_additem span:contains("Coded location qualifier")').parent().parent().parent().addClass('hidden');
    $('#cat_additem span:contains("Uniform Resource Identifier")').parent().parent().parent().addClass('hidden');
	$('#cat_additem span:contains("Price effective from")').parent().parent().parent().addClass('hidden');

    //Required fields
    $('#cat_additem .accessiondate label').addClass('required');
    $('#cat_additem .source label').addClass('required');
    $('#cat_additem .purchase label').addClass('required');
    $('#cat_additem .replacement label').addClass('required');
    $('#cat_additem .shelfloc label').addClass('required');
    $('#cat_additem .ccode label').addClass('required');
    $('#cat_additem .callnumber label').addClass('required');
    $('#cat_additem .bcode label').addClass('required');
    $('#cat_additem .itype label').addClass('required');

    //Headings
    if ($('#cat_additem #breadcrumbs:not(:contains("SHAREit"))').length) { //Excludes headings from shareit item adds
        $('#cat_additem span:contains("Withdrawn status")').parent().parent().parent().prepend('<h4 class="cathead">Statuses</h4><hr>');
        $('#cat_additem span:contains("Permanent location")').parent().parent().parent().prepend('<h4>Location</h4><hr>');
        $('#cat_additem span:contains("Date acquired")').parent().parent().parent().prepend('<h4>Acquisition</h4><hr>');
        $('#cat_additem span:contains("Shelving location")').parent().parent().parent().prepend('<h4>Classification</h4><hr>');
        $('#cat_additem span:contains("Non-public note")').parent().parent().parent().prepend('<h4>Notes</h4><hr>');
    }

    //Move
    $('#cat_additem .ccode').insertAfter('#cat_additem .shelfloc'); //ccode
    $('#cat_additem .public').insertAfter('#cat_additem .nonpublic'); //notes
    $('#cat_additem .accessiondate').insertAfter('#cat_additem .holdingbranch'); //date acquired
    $('#cat_additem .source').insertAfter('#cat_additem .accessiondate'); //source
    $('#cat_additem .purchase').insertAfter('#cat_additem .source'); //cost
    $('#cat_additem .replacement').insertAfter('#cat_additem .purchase'); //cost
    $('#cat_additem .itype').insertAfter('#cat_additem .copy'); //itemtype

  
    //Change ccode based on shelfloc
    $("[id*='tag_952_subfield_c_']").on('change', function() {
        var selected = $(this).val();
        catHelper(selected);
    });

    function catHelper(val) {
        var adultbook = ['100100ADFICCF', '100200ADFIC', '100250ADFICGN', '100300ADFICHF', '100400ADFICM', '100450ADFICHOL', '100500ADFICPBK', '100600ADFICPBKM', '100700ADFICPBKSF', '100800ADFICPBKW', '100850ADFICR', '100900ADFICSF', '101000ADFICW', '101100KFIC', '101200LPFICCF', '101300LPFIC', '101400LPFICM', '101500LPFICSF', '101600LPFICW', '101700ADFICILL', '101800YAFIC', '101900YAFICGN', '102000YAFICPBKF', '102100YAFICSF', '120100ADNFB', '120200ADNF', '120300ADNFREF', '120400ADNFTC', '120450AUTO', '120600KDNF', '120700KNF', '120800KRNF', '120900LPNFB', '121000LPNF', '121200ADNFQ', '121300ADNFPC', '121400ADNFILL', '121600YANFB', '121700YANF', '121800YAREF', '130300SRAREA', '130400ADSPANISH', '340225KSHC']
        var audiobook = ['260100ADAUDCAS', '260200ADAUDCD', '260250ADAUDMP3', '260300ADAUDPL', '260430ADAUDCDPC', '260460ADAUDCDILL', '260500YAAUDCAS', '260600YAAUDCD', '260700YAAUDPL', '280100JUVAUDBAC', '280200JUVAUDCAS', '280300JUVAUDCD', '280400JUVAUDPL']
        var bluray = ['220100ADVIDBLU', '240100JUVVIDBLU']
        var device = ['240300JUVVIDPL', '320400EREADER', '320440ADLPAD', '320450JUVLPAD']
        var dvd = ['220200ADVIDDVD', '220500ADVIDDVDPC', '220600ADVIDDVDILL', '240200JUVVIDDVD']
        var game = ['300150SOFPS', '300200SOFPS2', '300300SOFPS3', '300310SOFPS4', '300370SOF3DS', '300380SOFSWITCH', '300400SOFWII', '300410SOFWIIU', '300500SOFXBOX360', '300500SOFXBOXONE', '320250BGAMEPUZ']
        var juvbook = ['130450JUVSPANISH', '140100JUVFICBR', '140200JUVFICBB', '140300JUVFICBRA', '140325JUVFICBC', '140350JUVFICCHI', '140400JUVFICE', '140450JUVFICP', '140500JUVFIC', '140600JUVFICGN', '140700JUVFICHOL', '140800JUVFICLP', '140950JUVFICILL', '160100JUVNFB', '160150JUVNFBRA', '160175JUVNFHOL', '160200JUVNF', '160300JUVNFREF', '160400JUVNFILL', '170100ERYBODY']
        var microform = ['320700MICROFILM']
        var music = ['260400ADAUDMUS', '280500JUVAUDMUS']
        var periodical = ['180100ADMAG', '200100JUVMAG', '180200YAMAG']
        var rota = ['340200ROTA']
        var software = ['300050SOFCOMPPC', '300100SOFCOMP']
        var specialCollections = ['121500ADNFVF', '130100ECH', '130250NBC', '130500WMINGE', '140900JUVFICPAT', '320100ARTPRINT', '320200BAKING', '320300EQUIPMENT', '320500KITS', '320700PASS', '320800PHOTO', '320950PCKIT', '340205ARCHIVE', '340300SPECNEED']
        var stats = ['380100COMPUSE']
        var vhs = ['220400ADVIDVHS', '240400JUVVIDVHS']

        //Adult Books
        if ($.inArray(val, adultbook) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('AB').change();

        //Audiobooks
        } else if ($.inArray(val, audiobook) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('AUD').change();

        //Blu-rays
        } else if ($.inArray(val, bluray) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('BLU').change();

        //Devices
        } else if ($.inArray(val, device) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('DEV').change();

        //DVDs
        } else if ($.inArray(val, dvd) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('DVD').change();

        //Games
       } else if ($.inArray(val, game) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('GAM').change();

        //Juvenile Books
        } else if ($.inArray(val, juvbook) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('JB').change();

        //Microform
        } else if ($.inArray(val, microform) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('MIC').change();

        //Music
        } else if ($.inArray(val, music) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('MUS').change();

        //Periodicals
        } else if ($.inArray(val, periodical) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().show(500);
            $('[id*="tag_952_subfield_8_"]').val('PER').change();

        //Rotation
        } else if ($.inArray(val, rota) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('ROT').change();

        //Software
        } else if ($.inArray(val, software) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('SOF').change();

        //Special Collections
        } else if ($.inArray(val, specialCollections) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('SPC').change();

        //Stats
        } else if ($.inArray(val, stats) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('STT').change();

        //VHS
        } else if ($.inArray(val, vhs) !== -1) {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);
            $('[id*="tag_952_subfield_8_"]').val('VHS').change();

        //Everything Else
        } else {
            $('#cat_additem span:contains("Serial Enumeration")').parent().parent().parent().hide(500);

        }
    }
});
```
### IntranetUserCSS
```css
/*Add fake '*required' markers*/
#cataloguing_additem_newitem fieldset.rows label.required:after {
    color: red;
    content: " *";
}

/*Right-align field labels*/
#cataloguing_additem_newitem fieldset.rows label, #cataloguing_additem_newitem fieldset.rows span.label {
    width: 25%;
    text-align: right !important;
}

```