Tagator
==========
Tagator is a jQuery-based replacement for input boxes, making them tagging boxes. It supports searching, and affects the original input box directly, which is used as a comma serparated data container.
[You can see a demo here](http://opensource.qodio.com/tagator).


Usage
-----
###### include in head:
```html
<link rel="stylesheet" href="fm.tagator.jquery.css"/>
<script src="jquery-1.11.0.min.js"></script>
<script src="fm.tagator.jquery.js"></script>
```

###### to activate replacement:
```javascript
$('#inputBox').tagator();
```
If you don't wan't to meddle with scripting, there is an alternative to activate replacement, by using inline markup. 
```html
<input type="text" class="tagator" data-tagator-use-dimmer="true" data-tagator-autocomplete="['first', 'second', 'third']">
```


###### if you want to change settings:
```javascript
$('#inputBox').tagator({
    prefix: 'tagator_',           // CSS class prefix
    height: 'auto',               // auto or element
    useDimmer: false,             // dims the screen when result list is visible
    showAllOptionsOnFocus: false, // shows all options even if input box is empty
    allowAutocompleteOnly: false, // only allow the autocomplete options
    autocomplete: []              // this is an array of autocomplete options
});
```


CSS classes
-----------
Here is a list of all the css classes

Class                         | Description
----------------------------- | ------------------------------------------------------------------------------
`prefix_`element              | This is the new input box. It has some extra classes called `options-visible` and `options-hidden` which tell if the options list is visible or not
`prefix_`tags                 | The holder for the tags
`prefix_`tag                  | The tags
`prefix_`tag_remove           | The remove button for the tag
`prefix_`placeholder          | The placeholder element
`prefix_`input                | This is the input box for the tagator
`prefix_`textlength           | This is used to calculate the size of the input box
`prefix_`options              | The autocomplete options list holder. This is used together with `options-visible` or `options-hidden` to show or hide the autocomplete options
`prefix_`option               | This is a autocomplete option. It has an extra class called `active` which tells if the option is the active one
`prefix_`dimmer               | This is the dimmer


DOM Structure
-------------
* dimmer
* element: *containing the `options-visible`|`options-hidden` class*
    * textlength
    * tags
        * tag
            * tag_remove
        * tag...
    * placeholder
    * input
    * options
        * option: *containing the `active` class*
        * option...


jQuery methods
--------------
Method             | Description
------------------ | -----------
refresh            | This method is used to manually refresh the plugin. A scenario where this would be useful is if the data in the original input box is changed by some other script.
autocomplete       | This method is used to change/update the autocomplete list
destroy            | This method is used to remove the instance of the plugin from the input box and restore it to its original state.


###### Method usage
```javascript
$('#inputBox').tagator('refresh');
```
```javascript
$('#inputBox').tagator('autocomplete', ['tag1','tag2','tag3']);
```
```javascript
$('#inputBox').tagator('destroy');
```


Browser compatibility
---------------------
* IE 8+
* Chrome 2+
* Firefox 3+
* Safari 4+
* Opera 10.5+



Copyright and license
---------------------
The MIT License (MIT)

Copyright (c) 2013 Qodio

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
