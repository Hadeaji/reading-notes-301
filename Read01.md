# SMACSS and Responsive Web Design

## Responsive Web Design

Because of the variation of devices used to access the internet comes the question of how to build websites suitable for all users.

And here comes the responsive web design, also known as RWD.

### Responsive vs. Adaptive vs. Mobile
what exactly is the difference between all of them.

Responsive and adaptive web design are closely related, and often transposed as one in the same.
Responsive generally means to react quickly and positively to any change,
while adaptive means to be easily modified for a new purpose or situation.

the combination of them is the ideal and which term is used doesn’t make a difference.

the most popular technique lies within responsive web design,
favoring design that dynamically adapts to different browser and device viewports, changing layout and content along the way.

### Flexible Layouts

#### Relative Viewport Lengths

CSS3 introduced some new relative length units, specifically related to the viewport size of the browser or device. These new units include vw, vh, vmin, and vmax. Overall support for these new units isn’t great, but it is growing. In time they look to play a large roll in building responsive websites.

vw: Viewports width
vh: Viewports height
vmin: Minimum of the viewport’s height and width
vmax: Maximum of the viewport’s height and width

The formula is based around taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element.

#### Flexible Grid

Using the flexible grid formula we can take all of the fixed units of length and turn them into relative units.
target ÷ context = result

example:

`section,`
`aside {`
`margin: 1.858736059%; /*  10px ÷ 538px = .018587361 */`
`}`
`section {`
`float: left;`
`width: 63.197026%;    /* 340px ÷ 538px = .63197026 */`
`}`
`aside {`
  `float: right;`
  `width: 29.3680297%;  /* 158px ÷ 538px = .293680297 */`
`}`

For even more control within a flexible layout, you can also leverage the min-width, max-width, min-height, and max-height properties.

### Media Queries

Media queries were built as an extension to media types commonly found when targeting and including styles.
Media queries provide the ability to specify different styles for individual browser and device circumstances,
the width of the viewport or device orientation

#### Initializing Media Queries

##### There are a couple different ways to use media queries:

1. using the @media rule inside of an existing style sheet
2. importing a new style sheet using the @import rule
3. linking to a separate style sheet from within the HTML document

It is recommend to use the @media as in the first option to avoid any additional HTTP requests.

`@media all and (max-width: 1024px)`

Common media types include all, screen, print, tv, and braille.

The media query expression that follows the media type may include different media features and values,
which then allocate to be true or false.

When a media feature and value allocate to true, the styles are applied.
If the media feature and value allocate to false the styles are ignored.

#### Logical Operators in Media Queries

logical operators available for use within media queries, including `and`, `not`, and `only`.

The example below selects all media types between 800 and 1024 pixels wide:
`@media all and (min-width: 800px) and (max-width: 1024px)`

The not logical operator negates the query, specifying any query but the one identified.
In the example below the expression applies to any device that does not have a color screen.
Black and white or monochrome screens would apply here for example.

`@media not screen and (color)`

The only logical operator is a new operator and is not recognized by user agents using the HTML4 algorithm,
thus hiding the styles from devices or browsers that don’t support media queries.

Below, the expression selects only screens in a portrait orientation that have a user agent capable of rending
media queries.

`@media only screen and (orientation: portrait)`

#### Height & Width Media Features

The height and width features are based off the height and width of the viewport rendering area,the browser window
for example.
Values for these height and width media features may be any length unit, relative or absolute.

`@media all and (min-width: 320px) and (max-width: 780px)`

Within responsive design the most commonly used features include min-width and max-width.
These help build RW on desktops and mobile devices equally, avoiding any confusion with device features.

#### Using Minimum & Maximum Prefixes

The `min` prefix indicates a values of greater than or equal to.
the `max` prefix indicates a value of less than or equal to.

#### Orientation Media Feature

The `orientation` media feature determines if a device is in the `landscape` or `portrait` orientation.

#### Aspect Ratio Media Features

The aspect-ratio and device-aspect-ratio features specifies the width/height pixel ratio of the targeted rendering
area or output device.
The min and max prefixes are available to use with the different aspect ratio features, identifying a ratio above
or below that of which is stated.

`@media all and (min-device-aspect-ratio: 16/9)`

#### Resolution Media Feature

The `resolution` media feature specifies the resolution of the output device in pixel density, also known as dots per inch or DPI.

> The `resolution` media feature does accept the min and max prefixes.
> Additionally, the resolution media feature will accept dots per pixel (1.3dppx), dots per centimeter (118dpcm), and other length based resolution values.

`@media print and (min-resolution: 300dpi)`

#### Other Media Features

include identifying available output colors with use of the `color`, `color-index`, and `monochrome` features.

#### Identifying Breakpoints

Your instinct might be to write media query breakpoints around common viewport sizes as determined by different
device resolutions, such as 320px, 480px, 768px, 1024px, 1224px, and so. This is a bad idea.

new devices and resolutions are being released all of the time.
Trying to keep up with these changes could be an endless process.

### Mobile First

The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website,
then use media queries to add styles as the viewport grows.

A breakout of mobile first media queries might look at bit like the following.

Default styles first then media queries

`@media screen and (min-width: 400px)`

`@media screen and (min-width: 600px)`

`@media screen and (min-width: 1000px)`

`@media screen and (min-width: 1400px)`

example:

> Default media

`body {`
  `background: #ddd;`
`}`

> Media for larger devices

`@media screen and (min-width: 800px) {`
  `body {`
    `background-image: url("bg.png") 50% 50% no-repeat;`
  `}`
`}`

### Viewport

Sometimes they could use a little assistance though, particularly around identifying the viewport size, scale, and
resolution of a website. To remedy this, Apple invented the `viewport` meta tag.

#### Viewport Height & Width

Using the viewport meta tag with either the height or width values will define the height or width of the viewport
respectively.
Each value accepts either a positive integer or keyword.
For the height property the keyword device-height value is accepted, and for the width property the keyword
device-width is accepted.
Using these keywords will inherit the device’s default height and width value.

`<meta name="viewport" content="width=device-width">`

#### Viewport Scale

Use the `minimum-scale`, `maximum-scale`, `initial-scale`, and `user-scalable` properties,
To control how a website is scaled on a mobile device, and how users can continue to scale a website.

The `minimum-scale` and `maximum-scale` values determine how small and how large a viewport may be scaled.

these values should not be set to the same value as the initial-scale.
This would disable any zooming, which can be accomplished instead by using the user-scalable value.

Setting the user-scalable value to no will disable any zooming.

Turning off the ability to scale a website is a bad idea.
It harms accessibility and usability, preventing those with disabilities from viewing a website as desired.

`<meta name="viewport" content="user-scalable=yes">`

#### Viewport Resolution

The `target-densitydpi` viewport accepts a handful of values including `device-dpi`, `high-dpi`, `medium-dpi`, `low-dpi`, or an actual DPI number.

Using the `target-densitydpi` viewport value is rare, but extremely helpful when pixel by pixel control is needed.

`<meta name="viewport" content="target-densitydpi=device-dpi">`

#### Combining Viewport Values

Setting multiple values requires comma separating them within the content attribute value.

`<meta name="viewport" content="width=device-width, initial-scale=1">`

### Flexible Media

As viewports begin to change size media doesn’t always follow suit.
Images, videos, and other media types need to be scalable, changing their size as the size of the viewport changes.

One quick way to make media scalable is by using the `max-width` property with a value of 100%.
Doing so ensures that as the viewport gets smaller any media will scale down according to its containers width.

`img, video, canvas {`
  `max-width: 100%;`
`}`

#### Flexible Embedded Media

the `max-width` property doesn’t work well for all instances of media, specifically around iframes and embedded media.

To get embedded media to be fully responsive, the embedded element needs to be absolutely positioned within a
parent element.
The parent element needs to have a `width` of `100%` so that it may scale based on the width of the viewport.
The parent element also needs to have a `height` of `0` to trigger the `hasLayout` mechanism within Internet Explorer.

Example:

HTML:
`<figure>`
  `<iframe src="https://www.youtube.com/embed/4Fqg43ozz7A"></iframe>`
`</figure>`

CSS:
`figure {`
  `height: 0;`
  `padding-bottom: 56.25%; /* 16:9 */`
  `position: relative;`
  `width: 100%;`
`}`
`iframe {`
  `height: 100%;`
  `left: 0;`
  `position: absolute;`
  `top: 0;`
  `width: 100%;`
`}`


## Float

Float is a CSS positioning property.
In a print layout, images may be set into the page such that text wraps around them as needed.
This is commonly and appropriately called “text wrap”.

the boxes that hold the text can be told to honor the text wrap, or to ignore it.
Ignoring the text wrap will allow the words to flow right over the image like it wasn’t even there.

![ex](/files/Read01-1.png)

Setting the float on an element with CSS happens like this:
Example:

`#sidebar {`
  `float: right;`
`}`

### What are floats used for?

floats can be used to create **entire web layouts**

If we use float for our little avatar image, when that image changes size the text in the box will reflow to accommodate:

![ex](/files/Read01-2.png)

using relative positioning on container and absolute positioning on the avatar the text would be unaffected by the avatar and not be able to reflow on a size change.

![ex](/files/Read01-3.png)

#### Clearing the Float

Float’s sister property is `clear`. An element that has the `clear` property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.

![ex](/files/Read01-4.png)

`#footer {`
  `clear: both;`
`}`

![ex](/files/Read01-5.png)

Both is most commonly used, which clears floats coming from either direction.

and so it can be used this way:

![ex](/files/Read01-6.png)

#### Collapse

the floating items can affect the element that contains them (their “parent” element).
If this parent element contained nothing but floated elements, the height of it would literally collapse to nothing.

Collapsing almost always needs to be dealt with to prevent strange layout and cross-browser problems.
We fix it by clearing the float after the floated elements in the container but before the close of the container.

#### Techniques for Clearing Floats

1. The Empty Div Method: is quite literally, an empty div. `<div style="clear: both;"></div>`.

2. The Overflow Method: relies on setting the overflow CSS property on a parent element. If this property is set to auto or hidden on the parent element, the parent will expand to contain the floats.

3. The Easy Clearing Method: uses a clever CSS pseudo selector (:after) to clear floats.
Rather than setting the overflow on the parent, you apply an additional class like “clearfix” to it.
Then apply this CSS:

`.clearfix:after {`
   `content: ".";`
   `visibility: hidden;`
   `display: block;`
   `height: 0;`
   `clear: both;`
`}`

This will apply a small bit of content, hidden from view, after the parent element which clears the float.

So instead of this:

![ex](/files/Read01-7.png)

It will look like this:

![ex](/files/Read01-58.png)


#### Problems with Floats

1. **Pushdown:** is a symptom of an element inside a floated item being wider than the float itself (typically an image)
    Quick fix: Make sure you don’t have any images that do this, use `overflow: hidden` to cut off excess.
2. **Double Margin Bug:** is that if you apply a margin in the same direction as the float, it will double the margin
    Quick fix: set display: inline on the float, and don’t worry it will remain a block-level element.
3. **3px Jog:** is when text that is up next to a floated element is mysteriously kicked away by 3px like a weird forcefield around the float.
    Quick fix: set a width or height on the affected text.
4. **Bottom Margin Bug:** is when if a floated parent has floated children inside it, bottom margin on those children is ignored by the parent.
    Quick fix: using bottom padding on the parent instead.
