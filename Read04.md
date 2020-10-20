# Responsive Web Design and Regular Expressions

## Properties for the Parent (Grid Container)

### display

**grid** – generates a block-level grid
**inline-grid** – generates an inline-level grid

`.container {`
  `display: grid | inline-grid;`
`}`

### grid-template-columns && grid-template-rows

Defines the columns and rows of the grid with a space-separated list of values.
The values represent the track size, and the space between them represents the grid line.

- **track-size** can be a length, a percentage, or a fraction of the free space in the grid
- **line-name** an arbitrary name of your choosing

`.container {`
  `grid-template-columns:  50px 50%`
  `grid-template-rows:  1fr 2fr 3em`
`}`

![ex](/files/Read04-1.png)

### grid-template-areas

**grid-area-name:** the name of a grid area specified with grid-area
**. :** a period signifies an empty grid cell
**none:**  no grid areas are defined

Example:

`.item-a {`
  `grid-area: header;`
`}`
`.item-b {`
  `grid-area: main;`
`}`
`.item-c {`
  `grid-area: sidebar;`
`}`
`.item-d {`
  `grid-area: footer;`
`}`

`.container {`
  `display: grid;`
  `grid-template-columns: 50px 50px 50px 50px;`
  `grid-template-rows: auto;`
  `grid-template-areas:`
    `"header header header header"`
    `"main main . sidebar"`
    `"footer footer footer footer";`
`}`

![ex](/files/Read04-2.png)

### grid-template

A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.

**none** – sets all three properties to their initial values
**grid-template-rows** / **grid-template-columns**

Example:

`.container {`
  `grid-template:`
    `[row1-start] "header header header" 25px [row1-end]`
    `[row2-start] "footer footer footer" 25px [row2-end]`
    `/ auto 50px auto;`
`}`

### column-gap && row-gap && grid-column-gap && grid-row-gap

**line-size** – a length value

Example:

`.container {`
  `grid-template-columns: 100px 50px 100px;`
  `grid-template-rows: 80px auto 80px;`
  `column-gap: 10px;`
  `row-gap: 15px;`
`}`

### gap && grid-gap

**grid-row-gap grid-column-gap** – length values

Example:

`.container {`
  `grid-template-columns: 100px 50px 100px;`
  `grid-template-rows: 80px auto 80px;`
  `gap: 15px 10px;`
`}`

### justify-items

**start** aligns items to be flush with the start edge of their cell

**end** aligns items to be flush with the end edge of their cell

**center** aligns items in the center of their cell

**stretch** fills the whole width of the cell (this is the default)

### align-items

**start** aligns items to be flush with the start edge of their cell

**end** aligns items to be flush with the end edge of their cell

**center** aligns items in the center of their cell

**stretch**  fills the whole height of the cell (this is the default)

### place-items

**align-items / justify-items** The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.

### justify-content

**start** aligns the grid to be flush with the start edge of the grid container

**end** aligns the grid to be flush with the end edge of the grid container

**center** aligns the grid in the center of the grid container

**stretch** resizes the grid items to allow the grid to fill the full width of the grid container

**space-around** places an even amount of space between each grid item, with half-sized spaces on the far ends

**space-between** places an even amount of space between each grid item, with no space at the far ends

**space-evenly** places an even amount of space between each grid item, including the far ends

## Properties for the Children (Grid Items)

### grid-column-start && grid-column-end && grid-row-start && grid-row-end

**line** can be a number to refer to a numbered grid line, or a name to refer to a named grid line

**span number** the item will span across the provided number of grid tracks

**span name** the item will span across until it hits the next line with the provided name

**auto**  indicates auto-placement, an automatic span, or a default span of one

Example:

`.item-a {`
  `grid-column-start: 2;`
  `grid-column-end: five;`
  `grid-row-start: row1-start;`
  `grid-row-end: 3;`
`}`

### grid-column && grid-row

Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.

**start-line / end-line** each one accepts all the same values as the longhand version, including span

Example:

`.item-c {`
  `grid-column: 3 / span 2;`
  `grid-row: third-line / 4;`
`}`

### grid-area

**name** a name of your choosing
**row-start / column-start / row-end / column-end** can be numbers or named lines

Example:

`.item-d {`
  `grid-area: 1 / col4-start / last-line / 6;`
`}`

### justify-self

**start** aligns the grid item to be flush with the start edge of the cell

**end**  aligns the grid item to be flush with the end edge of the cell

**center**  aligns the grid item in the center of the cell

**stretch** fills the whole width of the cell (this is the default)

### align-self

**start** aligns the grid item to be flush with the start edge of the cell

**end** aligns the grid item to be flush with the end edge of the cell

**center** aligns the grid item in the center of the cell

**stretch** fills the whole height of the cell (this is the default)
