---
id: illitypedefaults
title: ILL Item Type Defaults
sidebar_label: ILL Item Type Defaults
---
We use the fast add framework for temporary ILL records of items from outside the consortium. The framework is setup with an authorized value list in the 300$a which determines format.
Some libraries use a secondary ILL item type on certain formats so they circulate for a shorter amount of time. For those libraries, this assigns the secondary item type to the 942$c when specific formats are chosen. 

## Breakdown

### Grab logged in library
Used to determine if the code should trigger for the currently logged in library.
```js
var libcode = $("#logged-in-info-full .logged-in-branch-code").text();
```	

### Define arrays
```js
var illshort = ['BR', 'DVD', 'GA', 'VHS'] //formats that use the shorter ILL item type
var activatedLibs = ['CANEY', 'COFFEYVILL', 'FREDONIA', 'FTSCOTT', 'IOLA', 'MOUNDCITY', 'WEIR'] //libraries that circulate certain formats at shorter lengths
```

### Compare variables and switch item type if proper criteria are met
The first `if` checks to see if the logged in library is in the array of libraries that need this code activated.

The second `if` checks to see if the value of the 300$a is in the illshort array, and if so, populates the 942$c with the ILLSHORT item type. Otherwise, the regular ILL item type is populated.
```js
if ($.inArray(libcode, activatedLibs)!== -1) {
    $('[id*="tag_300_subfield_a_"]').on('change', function() {
       if ($.inArray(this.value, illshort) !== -1) {
            $('[id*="tag_942_subfield_c_"]').val('ILLSHORT').change();
        } else {
            $('[id*="tag_942_subfield_c_"]').val('ILL').change();
        }
    });
}
```

## Complete CodeJS

### JS
```js
//Default to ILL:Shorter itype for Blu-rays, DVDs, Games and VHS at select libraries
$(document).ready(function() {
    var libcode = $("#logged-in-info-full .logged-in-branch-code").text();
    var illshort = ['BR', 'DVD', 'GA', 'VHS']
    var activatedLibs = ['CANEY', 'COFFEYVILL', 'FREDONIA', 'FTSCOTT', 'IOLA', 'MOUNDCITY', 'WEIR']
    if ($.inArray(libcode, activatedLibs)!== -1) {
        $('[id*="tag_300_subfield_a_"]').on('change', function() {
            if ($.inArray(this.value, illshort) !== -1) {
                $('[id*="tag_942_subfield_c_"]').val('ILLSHORT').change();
            } else {
                $('[id*="tag_942_subfield_c_"]').val('ILL').change();
            }
        });
    }
});
```