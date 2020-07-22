Turn any HTML element into a grid container by setting its _**display**_ property to _**grid.**_ This gives you the ability to use all the other properties associated with CSS Grid.

**Note:** In CSS Grid, the parent element is referred to as the container and its children are called items.

### <ins>Add Columns with grid-template-columns

You need to define the structure of the grid as well. To add some columns to the grid, use the _**grid-template-columns**_ property on a grid container as demonstrated below:

```
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

This will give your grid two columns that are each **50px wide**. The number of parameters given to the _**grid-template-columns**_ property indicates the **number** of columns in the grid, and the value of each parameter indicates the **width** of each column.

### <ins>Add Rows with grid-template-rows

To adjust the rows manually, use the _**grid-template-rows**_ property.

```
 .container {
    font-size: 40px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 100px 100px 100px ;
    grid-template-rows: 50px 50px;
  }
```

### <ins>Use CSS Grid units to Change the Size of Columns and Rows

You can use absolute and relative units like **px** and **em** in CSS Grid to define the _size_ of rows and columns. You can use these as well:

- _**fr:**_ sets the column or row to a fraction of the available space,

- _**auto:**_ sets the column or row to the width or height of its content automatically,

- _**%:**_ adjusts the column or row to the percent width of its container.

Here's the code that generates the output in the preview:

`grid-template-columns: auto 50px 10% 2fr 1fr;`

This snippet creates **five** columns. The first column is **as wide as its content**, the second column is **50px**, the third column is **10% of its container**, and for the last two columns; the remaining space is divided into three sections, **two** are allocated for the fourth column, and **one** for the fifth.

### <ins>Create a Column Gap Using grid-column-gap

Sometimes you want a gap in between the columns. To add a gap between the columns, use the _**grid-column-gap**_ property like this:

`grid-column-gap: 10px;`

### <ins>Create a Row Gap using grid-row-gap

You can add a gap in between the rows of a grid using _**grid-row-gap**_ in the same way that you add a gap in between columns.

```
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-row-gap:5px;
  }
```

### <ins>Add Gaps Faster with grid-gap

_**grid-gap**_ is a shorthand property for _**grid-row-gap**_ and \_**grid-column-gap** that's more convenient to use. If grid-gap has **one** value, it will create a **gap between all rows and columns**. However, if there are **two** values, it will use the first one to **set the gap between the rows** and the second value for the **columns**.

```
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px 20px;
  }
```

### <ins>Use grid-column to Control Spacing

The _**grid-column**_ property is the first one for use on the grid items themselves.

The hypothetical horizontal and vertical lines that create the grid are referred to as _**lines**_. These lines are numbered starting with **1** at the top left corner of the grid and move right for columns and down for rows, counting upward.

To control the amount of columns an item will consume, you can use the _**grid-column**_ property in conjunction with the _**line**_ numbers you want the item to start and stop at.

Here's an example:

`grid-column: 1 / 3;`

This will make the item start at the first vertical line of the grid on the left and span to the 3rd line of the grid, consuming two columns.

### <ins>Use grid-row to Control Spacing

You can make items consume multiple rows just like you can with columns. You define the horizontal lines you want an item to start and stop at using the _**grid-row**_ property on a grid item.

```
.item5 {
    background: PaleGreen;
    grid-column: 2 / 4;
    grid-row: 2/4;
  }
```

### <ins>Align an Item Horizontally using justify-self

In CSS Grid, the content of each item is located in a box which is referred to as a _**cell**_. You can align the content's position within its cell horizontally using the _**justify-self**_ property on a grid item. By default, this property has a value of _**stretch**_, which will make the content _fill the whole width of the cell_. This CSS Grid property accepts other values as well:

- _**start:**_ aligns the content at the left of the cell,

- _**center:**_ aligns the content in the center of the cell,

- _**end:**_ aligns the content at the right of the cell.

```
  .item2 {
    background: LightSalmon;
    justify-self:center;
  }
```

### <ins>Align an Item Vertically using align-self

Just as you can align an item horizontally, there's a way to align an item vertically as well. To do this, you use the _**align-self**_ property on an item. This property accepts all of the same values as _**justify-self**_.

```
.item3 {
    background: PaleTurquoise;
    align-self:end;
  }
```

### <ins>Align All Items Horizontally using justify-items

Sometimes you want all the items in your CSS Grid to share the same alignment. You can align them _all at once horizontally_ by using _**justify-items**_ on your grid container. This property can accept all the same values, the difference being that it will move _all the items in our grid_ to the desired alignment.

```
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
    justify-items:center;
  }
```

### <ins>Align All Items Vertically using align-items

Using the _**align-items**_ property on a grid container will set the _vertical alignment_ for all the items in our grid.

```
 .container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
    align-items: end;
  }
```

### <ins>Divide the Grid Into an Area Template

You can group cells of your grid together into an _**area**_ and give the area a custom name. Do this by using _**grid-template-areas**_ on the container like this:

```
grid-template-areas:
  "header header header"
  "advert content content"
  "footer footer footer";
```

The code above merges the top three cells together into an area named _**header**_, the bottom three cells into a _**footer**_ area, and it makes two areas in the middle row; _**advert and content**_.

**Note:** Every word in the code represents a cell and every pair of quotation marks represent a row. In addition to custom labels, you can use a period (**.**) to designate an empty cell in the grid.

### <ins> Place Items in Grid Areas Using the grid-area Property

After creating an _area_'s template for your grid container, you can place an item in your custom area by referencing the name you gave it. To do this, you use the _**grid-area**_ property on an item like this:

```
.item1 {
  grid-area: header;
}
```

This lets the grid know that you want the _**item1**_ class to go in the area named _**header**_. In this case, the item will use the entire top row because that whole row is named as the header area.

### <ins>Use grid-area Without Creating an Areas Template

The _**grid-area**_ property can be used in another way. If your grid doesn't have an areas template to reference, you can create an area on the fly for an item to be placed like this:

`item1 { grid-area: 1/1/2/4; }`

This is using the line numbers you learned about earlier to define where the area for this item will be. The numbers in the example above represent these values:

`grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;`

So the item in the example will consume the rows between lines 1 and 2, and the columns between lines 1 and 4.

### <ins>Reduce Repetition Using the repeat Function

Let's say you want a grid with **100** rows of the same height. It isn't very practical to insert 100 values individually. Fortunately, there's a better way - by using the _**repeat**_ function to specify the number of times you want your column or row to be repeated, followed by a comma and the value you want to repeat.

Here's an example that would create the 100 row grid, each row at 50px tall.

`grid-template-rows: repeat(100, 50px);`

You can also repeat multiple values with the repeat function and insert the function amongst other values when defining a grid structure. Here's what that looks like:

`grid-template-columns: repeat(2, 1fr 50px) 20px;`

This translates to:

`grid-template-columns: 1fr 50px 1fr 50px 20px;`

**Note:** The _**1fr 50px**_ is repeated twice followed by 20px.

### <ins>Limit Item Size Using the minmax Function

There's another built-in function to use with _**grid-template-columns**_ and _**grid-template-rows**_ called _**minmax.**_ It's used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for your item. Here is an example:

`grid-template-columns: 100px minmax(50px, 200px);`

In the code above, _**grid-template-columns**_ is set to create two columns; the first is 100px wide, and the second has the minimum width of 50px and the maximum width of 200px.

```
 .container {
    display: grid;
    grid-template-columns: repeat(3, minmax(90px, 1fr));
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
```

### <ins>Create Flexible Layouts Using auto-fill

The repeat function comes with an option called _**auto-fill**_. This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. You can create flexible layouts when combining _**auto-fill** with _**minmax**, like this:

`repeat(auto-fill, minmax(60px, 1fr));`

When the container changes size, this setup keeps inserting 60px columns and stretching them until it can insert another one.

**Note:** If your container can't fit all your items on one row, it will move them down to a new one.

### <ins>Create Flexible Layouts Using auto-fit

_**auto-fit**_ works almost identically to _**auto-fill**_. The only difference is that when the container's size exceeds the size of all the items combined, _**auto-fill**_ keeps inserting empty rows or columns and pushes your items to the side, while _**auto-fit**_ collapses those empty rows or columns and stretches your items to fit the size of the container.

**Note:** If your container can't fit all your items on one row, it will move them down to a new one.

```
  .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
    grid-template-rows: repeat(auto-fit, minmax(60px,1fr));
    grid-gap: 10px;
  }
```

### <ins>Use Media Queries to Create Responsive Layouts

CSS Grid can be an easy way to make your site more responsive by using media queries to rearrange grid areas, change dimensions of a grid, and rearrange the placement of items.

```
  @media (min-width: 400px){
    .container{
      grid-template-areas:
        "header header"
        "advert content"
        "footer footer";
    }
```

### <ins>Create Grids within Grids

Turning an element into a grid only affects the behavior of its direct descendants. So by turning a direct descendant into a grid, you have a grid within a grid.

```
 .item3 {
    background: PaleTurquoise;
    grid-area: content;
    display: grid;
    grid-template-columns: auto 1fr;
  }
```
