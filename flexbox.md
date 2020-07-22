### <ins>Use display: flex to Position Two Boxes

Placing the CSS property _**display: flex;**_ on an element allows you to use other flex properties to build a responsive page.

```
  #box-container {
    height: 500px;
    display:flex;
  }
```

### <ins>Use the flex-direction Property to Make a Row

Adding _**display: flex**_ to an element turns it into a flex container. This makes it possible to align any children of that element into rows or columns. You do this by adding the _**flex-direction**_ property to the parent item and setting it to row or column.

Other options for _**flex-direction**_ are row-reverse and column-reverse.
**Note:** The default value for the _**flex-direction**_ property is _**row.**_

```
  #box-container {
    display: flex;
    height: 500px;
    flex-direction:row-reverse;
  }
```

### <ins>Align Elements Using the justify-content Property

Sometimes the flex items within a flex container do not fill all the space in the container. It is common to want to tell CSS how to align and space out the flex items a certain way. Fortunately, the _**justify-content**_ property has several options to do this.

Setting a flex container as a row places the flex items side-by-side from left-to-right. A flex container set as a column places the flex items in a vertical stack from top-to-bottom. For each, the direction the flex items are arranged is called the _**main axis.**_ For a row, this is a horizontal line that cuts through each item. And for a column, the main axis is a vertical line through the items.

There are several options for how to space the flex items along the line that is the main axis. One of the most commonly used is _**justify-content: center;**_, which aligns all the flex items to the **center** inside the flex container. Others options include:

- _**flex-start:**_ aligns items to the **start** of the flex container. For a row, this pushes the items to the left of the container. For a column, this pushes the items to the top of the container. This is the default alignment if no _**justify-content**_ is specified.

- _**flex-end:**_ aligns items to the **end** of the flex container. For a row, this pushes the items to the right of the container. For a column, this pushes the items to the bottom of the container.

- _**space-between:**_ aligns items to the **center of the main axis**, with extra space placed between the items. The first and last items are pushed to the very edge of the flex container.
  For example, in a row the first item is against the left side of the container, the last item is against the right side of the container, then the remaining space is distributed evenly among the other items.

- _**space-around:**_ similar to _**space-between**_ but the **first and last items are not locked to the edges of the container**, the space is distributed around all the items with a half space on either end of the flex container.

- _**space-evenly:**_ Distributes space **evenly** between the flex items with a full space at either end of the flex container.

```
 #box-container {
    background: gray;
    display: flex;
    height: 500px;
    justify-content:center;
  }
```

### <ins>Align Elements Using the align-items Property

The _**align-items**_ property is similar to _**justify-content.**_

The different values available for _**align-items**_ include:

- _**flex-start:**_ aligns items to the start of the flex container. For rows, this aligns items to the top of the container. For columns, this aligns items to the left of the container.

- _**flex-end:**_ aligns items to the end of the flex container. For rows, this aligns items to the bottom of the container. For columns, this aligns items to the right of the container.

- _**center:**_ align items to the center. For rows, this vertically aligns items (equal space above and below the items). For columns, this horizontally aligns them (equal space to the left and right of the items).

- _**stretch:**_ stretch the items to fill the flex container. For example, rows items are stretched to fill the flex container top-to-bottom. This is the default value if no _**align-items**_ value is specified.

- _**baseline:**_ align items to their baselines. Baseline is a text concept, think of it as the line that the letters sit on.

```
 #box-container {
    background: gray;
    display: flex;
    height: 500px;
    align-items: center;
  }
```

### <ins> Use the flex-wrap Property to Wrap a Row or Column

The _**flex-wrap**_ property tells CSS to wrap items. This means extra items move into a new row or column. The break point of where the wrapping happens depends on the size of the items and the size of the container.

CSS also has options for the direction of the wrap:

- _**nowrap:**_ this is the default setting, and does not wrap items.

- _**wrap:**_ wraps items from left-to-right if they are in a row, or top-to-bottom if they are in a column.

- _**wrap-reverse:**_ wraps items from right-to-left if they are in a row, or bottom-to-top if they are in a column.

```
 #box-container {
    background: gray;
    display: flex;
    height: 100%;
    flex-wrap:wrap;
  }
```

### <ins> Use the flex-shrink Property to Shrink Items

The _**flex-shrink**_ property allows an item to shrink if the flex container is too small.

The _**flex-shrink**_ property takes numbers as values. The higher the number, the more it will shrink compared to the other items in the container. For example, if one item has a _**flex-shrink**_ value of **1** and the other has a _**flex-shrink**_ value of **3**, the one with the value of **3** will shrink three times as much as the other.

```
#box-1 {
    background-color: dodgerblue;
    width: 100%;
    height: 200px;
    flex-shrink:1;
  }

#box-2 {
    background-color: orangered;
    width: 100%;
    height: 200px;
    flex-shrink:2;
  }
```

### <ins> Use the flex-grow Property to Expand Items

The _**flex-grow**_ property controls the size of items when the parent container expands.If one item has a _**flex-grow**_ value of **1** and the other has a _**flex-grow**_ value of **3**, the one with the value of **3** will grow three times as much as the other.

```
 #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-grow:1;
  }

#box-2 {
    background-color: orangered;
    height: 200px;
    flex-grow:2;
  }
```

### <ins> Use the flex-basis Property to Set the Initial Size of an Item

The _**flex-basis**_ property specifies the initial size of the item before CSS makes adjustments with _**flex-shrink**_ or _**flex-grow.**_

The units used by the _**flex-basis**_ property are the same as other size properties (**px**, **em**, **%**, etc.). The value _**auto**_ sizes items based on the content.

```
#box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-basis:10em;
  }

#box-2 {
    background-color: orangered;
    height: 200px;
    flex-basis:20em;
  }
```

### <ins> Use the flex Shorthand Property

There is a shortcut available to set several flex properties at once. The _**flex-grow**_, _**flex-shrink,**_ and _**flex-basis**_ properties can all be set together by using the _**flex**_ property.

For example, _**flex: 1 0 10px;**_ will set the item to _**flex-grow: 1;**_, _**flex-shrink: 0;**_, and _**flex-basis: 10px;**_.

The default property settings are _**flex: 0 1 auto;**_.

```
#box-2 {
    background-color: orangered;
    height: 200px;
    flex: 1 1 150px;
  }
```

### <ins>Use the order Property to Rearrange Items

The _**order**_ property is used to tell CSS the **order** of how flex items appear in the flex container. By default, items will appear in the same order they come in the source HTML. The property takes numbers as values, and negative numbers can be used.

```
 #box-1 {
    background-color: dodgerblue;
    height: 200px;
    width: 200px;
    order:2;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    width: 200px;
    order:1;
  }

```

### <ins>Use the align-self Property

The final property for flex items is _**align-self**_. This property allows you to adjust each item's alignment **individually**, instead of setting them all at once. This is useful since other common adjustment techniques using the CSS properties _**float**_, _**clear**_, and _**vertical-align**_ do not work on flex items.

_**align-self**_ accepts the same values as _**align-items**_ and will override any value set by the _**align-items**_ property.

```
#box-1 {
    background-color: dodgerblue;
    height: 200px;
    width: 200px;
    align-self: center;
  }

#box-2 {
    background-color: orangered;
    height: 200px;
    width: 200px;
    align-self:flex-end;
  }
```

Source [freeCodeCamp](https://www.freecodecamp.org/learn)
