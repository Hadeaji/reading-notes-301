# Flexbox and Templating

## Javascript Templating

Javascript templating is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source.

The template is HTML markup, with added templating tags that will either insert variables or run programming logic.

The template engine then replaces variables and instances declared in a template file with actual values
at runtime, and convert the template into an HTML file sent to the client.

### Mustache

![ex](/files/Read03-1.png)

Mustache is a logic-less template syntax.
It can be used for HTML, config files, source code — anything.

**It is often referred to as “logic-less” because there are no if statements, else clauses, or for loops.**

**Instead, there are only tags. Some tags are replaced with a value, some nothing, and others a series of values.**

mustache.js is an implementation of the mustache template system in JavaScript.
It is often considered the base for JavaScript templating.
And, since mustache supports various languages, we don’t need a separate templating system on the server side.

`Mustache.render(“Hello, {{name}}”, { name: “Sherlynn” });`

returns: Hello, Sherlynn

#### Mustache-Express

If you intend you use mustache with Node and Express, you can use mustache-express.
Mustache Express lets you use Mustache and Express together easily.

#### How to install it:

- With Yarn: `$ yarn add mustache-express`
- or with NPM: `$ npm install mustache --save`

Configure mustache-express in your server.js/app.js/index.js file:

![ex](/files/Read03-2.png)

Create a views folder and add some html view templates (e.g. hello.html):

Then in the router configuration, use res.render(TEMPLATE_NAME, JSON_DATA). Example:

`res.render('hello', {"name": "Sherlynn"})`

## Guide to Flexbox

### Properties for the Parent (flex container)

#### **display**

This defines a flex container; inline or block depending on the given value.
It enables a flex context for all its direct children.

`.container {`
  `display: flex;`     *or inline-flex*
`}`

#### **flex-direction**

![ex](/files/Read03-3.png)

**row (default):** left to right in ltr; right to left in rtl
**row-reverse:** right to left in ltr; left to right in rtl
**column:** same as row but top to bottom
**column-reverse:** same as row-reverse but bottom to top

#### **flex-wrap**

![ex](/files/Read03-4.png)

**nowrap (default):** all flex items will be on one line
**wrap:** flex items will wrap onto multiple lines, from top to bottom.
**wrap-reverse:** flex items will wrap onto multiple lines from bottom to top.

#### **flex-flow**

This is a shorthand for the flex-direction and flex-wrap properties,
which together define the flex container’s main and cross axes. The default value is row nowrap.

`.container {`
  `flex-flow: column wrap;`
`}`

#### **justify-content**

![ex](/files/Read03-5.png)

**flex-start (default):** items are packed toward the start of the flex-direction.
**flex-end:** items are packed toward the end of the flex-direction.
**start:** items are packed toward the start of the writing-mode direction.
**end:** items are packed toward the end of the writing-mode direction.
**left:** items are packed toward left edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
**right:** items are packed toward right edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
**center:** items are centered along the line
**space-between:** items are evenly distributed in the line; first item is on the start line, last item on the end line
**space-around:** items are evenly distributed in the line with equal space around them.
***Note*** that visually the spaces aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
**space-evenly:** items are distributed so that the spacing between any two items (and the space to the edges) is equal.

#### **align-items**

![ex](/files/Read03-6.png)

This defines the default behavior for how flex items are laid out along the cross axis on the current line.
> *Think of it as the justify-content version for the cross-axis*

**stretch (default):** stretch to fill the container (still respect min-width/max-width)
**flex-start / start / self-start:** items are placed at the start of the cross axis.
The difference between these is subtle, and is about respecting the flex-direction rules or the writing-mode rules.
**flex-end / end / self-end:** items are placed at the end of the cross axis.
The difference again is subtle and is about respecting flex-direction rules vs. writing-mode rules.
**center:** items are centered in the cross-axis
**baseline:** items are aligned such as their baselines align

#### **align-content**

![ex](/files/Read03-7.png)

This aligns a flex container’s lines within when there is extra space in the cross-axis,
similar to how justify-content aligns individual items within the main-axis.

**normal (default):** items are packed in their default position as if no value was set.
**flex-start / start:** items packed to the start of the container.
The (more supported) flex-start honors the flex-direction while start honors the writing-mode direction.
**flex-end / end:** items packed to the end of the container.
The (more support) flex-end honors the flex-direction while end honors the writing-mode direction.
**center:** items centered in the container
**space-between:** items evenly distributed; the first line is at the start of the container while the last one is at the end
**space-around:** items evenly distributed with equal space around each line
**space-evenly:** items are evenly distributed with equal space around them
**stretch:** lines stretch to take up the remaining space

### Properties for the Children(flex items)

#### **order**

![ex](/files/Read03-8.png)

By default, flex items are laid out in the source order.

the order property controls the order in which they appear in the flex container.

`.item {`
  `order: 5;`            *default is 0*
`}`

#### **flex-grow**

![ex](/files/Read03-9.png)

This defines the ability for a flex item to grow if necessary.

It accepts a unitless value that serves as a proportion. 

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children.
If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).

`.item {`
  `flex-grow: 4;`           *default 0*
`}`

#### **flex-shrink**

This defines the ability for a flex item to shrink if necessary.

`.item {`
  `flex-shrink: 3;`         *default 1*
`}`

> Negative numbers are invalid.

#### **flex-basis**

This defines the default size of an element before the remaining space is distributed.

The `auto` keyword means **“look at my width or height property”**

The `content` keyword means **“size it based on the item’s content”**

`.item {`
  `flex-basis:  | auto;`   *default auto*
`}`

> If set to 0, the extra space around content isn’t factored in.
> If set to auto, the extra space is distributed based on its flex-grow value.

#### **flex**

This is the shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined.

`.item {`
  `flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]`
`}`

> **It is recommended that you use this shorthand property rather than set the individual properties.**

#### **align-self**

![ex](/files/Read03-10.png)

This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

`.item {`
  `align-self: auto | flex-start | flex-end | center | baseline | stretch;`
`}`
