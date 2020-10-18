# jQuery, Events, and The DOM

## What Is jQuery?

JS file that you use in your web pages by including it in your code
let you find elements ussing the CSS selectors

1. First find the element using the selestor, EX:
   `$('#cup')`
2. Then add the method so you do something with it, EX:
    `$('#cup').addClass('item');`

### Basic jQuery Example:

![ex](/files/Read02-1.png)

![ex](/files/Read02-2.png)

## Why We Use It?

1. jQuery doesn't do anything you cannot achieve with pure JavaScript.
It Just Make Coding Simpler.

2. Instead of calling the element like always you can use the CSS selector in a much shorter sentence
And you can do so many COMMON tasks that requires time in a really easier, simpler and faster way

3. Cross-Browser Compatibility: jQuery automatically handles the inconsistent ways in which browsers select
elements and handle events, so you do not need to write cross-browser fallback code

jQuery's motto is **"Write less, do more,"**
because it allows you to achieve the same goals but in fewer lines of code

## jQuery Selectoion

Single Element:
   `$('ul')`
if there is one ul the jQuery will contain a refrence for just one element

Multiple Elementa:
   `$('li')`
if there is more than one li the jQuery will contain an array for the elements start fron index 0

## How To Get And Set Data

Get Info:
for example you want to get the content of li element you may do it as:
`var content = $('li').html();`

Set Info:
`$('li').html('What Ever you Want to Write');`

### Looping

In JavaScript, if you wanted to do the same thing to several elements, you would need to write code to loop through
all of the elements you selected.

With jQuery, when a selector returns multiple elements, you can update all of them using the one method.
There is no need to use a loop.

### Chaining

If you want to use more than one jQuery method on the same selection of elements, you can list several methods at a
time using dot notation to separate each one, as below.

`$('li[id!="one"]').hide().delay(SOO).fadeln(1400);`

## Checking The Page If It Is Ready To Work With

`$(document).ready(function(){`

   > *"And you write script in here so it work after the page finishes loading"*

`});`

there is a sorter method goes like this:

`$(function(){`

   > *"And you write script in here so it work after the page finishes loading"*

`})`

### GETTING ELEMENT CONTENT

`.html()` : will return the whole content with the html tags inside of the element
`.text()` : will only return the text content of the element

### UPDATING ELEMENTS 

`.html()` :
This method gives every element in the matched set the same new content.
The new content may include HTML.

`.text()` :
This method gives every element in the matched set the same new text content
Any markup would be shown as text.

`.replaceWith()` :
This method replaces every element in a matched set with new content.
It also returns the replaced elements.

`.remove()` :
This method removes all of the elements in the matched set.

### INSERTING ELEMENTS 

1. Create the new elements in a jQuery object
This jQuery object in turn contains an <1 i> element with a class attribute and some text:
    `var $newltem = $('<li class="new">item</ li>');`

2. Use a method to insert the content into the page

    - `.before()`
    This method inserts content before the selected element(s) .

    - `.prepend()`
    This method inserts content inside the selected element(s), after the opening tag.

    - `.after()`
    This method inserts content after the selected element(s).

    - `.append()`
    This method inserts content inside the selected element(s), before the closing tag.

### GETTING AND SETTING ATTRIBUTE VALUES

`.attr()`
This method can get or set a specified attribute and its value.
To get the value of an attribute,you specify the name of the attribute in the parentheses.

`.removeAttr()`
This method removes a specified attribute (and its value).
You just specify the name of the attribute that you want to remove.

`.addClass()`
This method adds a new value to the existing value of the class attribute.

`.removeClass()`
This method removes a value from the class attribute, leaving any other class names

### GETTING & SETTING CSS PROPERTIES

`.css()` method lets you retrieve and set the values of CSS properties.

- HOW TO GET A CSS PROPERTY
You can assign it to var as shown:
`var backgroundColor = $('li').css('background-color');`

- HOW TO SET A CSS PROPERTY
You can add set after calling the property:
`$('li').css('background- color','1272727');`

- SETTING MULTIPLE PROPERTIES
You can set multiple properties using object literal notation:

`$('1i').css({`
`'background-color':'#272727',`
`'font-family':'Courier'`
`});`

### WORKING WITH EACH ELEMENT IN A SELECTION

jQuery allows you to recreate the functionality of a loop on a selection of elements, using the `.each()` method.
you can access the current element using the `this` keyword.

`$('li').each(function() {`
`$(this).append(' <em class="order">' +ids+ '</ em>');`
`});`

### EVENT METHODS

The `.on()` method is used to handle all events.

`$('li').on('click', function(){`
    `$(this).addClass( complete');`
`});`

### JQUERY EVENTS

**UI**          focus , blur, change
**KEYBOARD**    input, keydown, keyup, keypress
**MOUSE**       click, dblclick, mouseup, mousedown,mouseover, mousemove, mouseout, hover
**FORM**        submit, select, change
**DOCUMENT**    ready , load, unload
**BROWSER**     error, resize , scro11

### THE EVENT OBJECT

![ex](/files/Read02-3.png)

### LOADING JQUERY FROM A CDN

![ex](/files/Read02-4.png)

> *The position of `<script>` elements can affect how quickly a web page seems to load.*

### WHERE TO PLACE YOUR SCRIPTS

If In the Head: the page will take more time to load also the DOM content is not loaded yet
If In the page: you will have harder time coding and when you create elements the code have to be wher they will be
Before the closing of the body tag: the best place the script is loaded last and the DOm is already loaded

### 6 Reasons for Pair Programming:

1. Greater efficiency
2. Engaged collaboration
3. Learning from fellow students
4. Social skills
5. Job interview readiness
6. Work environment readiness

And i suppose those point don't need explaining