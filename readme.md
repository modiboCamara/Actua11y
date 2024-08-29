# Tips and Tricks

### Why does my item fill the container when flex-direction is set to column

When you use Flexbox and set the flex-direction to column, the flex items are arranged vertically, one below the other. By default, in a column layout, the flex items will stretch to fill the entire width of the flex container unless otherwise specified.

### Why This Happens:

Default align-items Property: The align-items property in Flexbox controls how flex items are aligned along the cross axis (which is horizontal when flex-direction: column is used). The default value for align-items is stretch, which causes flex items to stretch to fill the entire width of the flex container.
How to Control the Width:
If you don’t want the flex items to stretch to the full width of the container, you can change the align-items property.

### Solution:

Use

```css
.flex-container {
  align-items: flex-start;
}
```

This aligns the items to the start of the cross axis (left side, if the direction is left-to-right).

```css
.container {
  display: flex;
  flex-direction: column;
  align-items: flex-start; /* Items won't stretch to the full width */
}
```

### Specify a Width on Flex Items:

You can also set a specific width for the flex items if you don't want them to stretch.

```css
.item {
  width: 50%; /* Flex items will be 50% of the container's width */
}
```

### Example

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

```css
.container {
  display: flex;
  flex-direction: column;
  align-items: flex-start; /* Prevents items from stretching to full width */
  /* or use align-items: center; */
}

.item {
  background-color: lightblue;
  padding: 10px;
  margin: 5px;
  width: auto; /* Adjusts the width to the content */
}
```
