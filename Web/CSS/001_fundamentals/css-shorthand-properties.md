# CSS Shorthand Properties

- Shorthand properties are a convenient way to set multiple related properties with a single declaration
- Shorthands are designed to keep css code _clear, and concise_

## Shorthand Property Overrides

- Shorthands allow you to omit values when settings properties, but if you do, the omitted _values will be set to their initial value_
- This will cause overrides to occur when you use a shorthand property after setting individual properties, as the omitted values will reset to their initial state

## Order of Values

- When setting values for some shorthand properties, the browser will figure out which values correspond to which properties, such as `border`, where the order of values doesn't matter. 
- The browser can determine which value corresponds to `border-width`, `border-style`, and `border-color` based on the type of value provided (e.g., a length for width, a keyword for style, and a color for color)
- Other shorthand values are ambiguous, such as `margin`
- For _ambiguous shorthand properties_, **order of values** matters in this case clockwise order beginning at the top.

### Four Side Shorthands

- Use the _mnemonic_ **TRouBLe** to for the order of values for the `margin` and `padding` shorthands:
  - `margin: top right bottom left;`
  - If only one value is provided, it applies to all sides: `margin: 10px;` (top, right, bottom, left)
  - If two values are provided, the first applies to the top and bottom, and the second applies to the left and right: `margin: 10px 20px;` (top/bottom: 10px, left/right: 20px)
  - If three values are provided, the first applies to the top, the second applies to the left and right, and the third applies to the bottom: `margin: 10px 20px 30px;` (top: 10px, left/right: 20px, bottom: 30px)
  - If four values are provided, they apply to the top, right, bottom, and left respectively: `margin: 10px 20px 30px 40px;` (top: 10px, right: 20px, bottom: 30px, left: 40px)


### Two Side Shorthands 

- Two side shorthands apply to properties that have a _horizontal_ and _vertical_ component,
- properties like `background-position` and `text-shadow`
- The order of these values follows the _cartesian grid_ (x, y). Horizontal values first, followed by vertical values.
- For example, `background-position: 50% 50%;` sets the horizontal position

### Truncated Shorthand Notations

- For ordered values, that follow the order _top, right, bottom, left_ they also support truncated notations.
- Truncated notations allow to specify fewer values, the values that are not specified will be copy the values from the set values.
- When a side from the order is not provided that side will take the value from the opposite.
- Example, `margin: 10px 20px`. 
  - Here the _top_ and _right_ values are only provided
  - Thus, the _bottom_ value will take the opposite side's value, which is the _top_ value of `10px`
  - The _left_ value will take the opposite side's value, which is the _

## Example

```html
<style>
  /* Setting border shorthand property */
  .box {
    border-width: 5px;     /* set width */
    border-style: dashed;  /* set style */
    border-color: green;   /* set color */

    /* This shorthand overrides all three.
       Missing values revert to their initial value. */
    border: 2px solid;     
    /* The above shorthand is equivalent to setting the values to the following: */
    border-width: 2px;
    border-style: solid;  
    border-color: initial; /* resets color to default */
  }
</style>

<div class="box">Border shorthand overrides earlier settings</div>
```

## Example (Ordered Values)

```html
<!-- Ordered values for margin shorthand (TRouBLe) -->
<style>
  .box1 { margin: 10px; }                 /* all sides = 10px */
  .box2 { margin: 10px 20px; }            /* top/bottom = 10px, left/right = 20px */
  .box3 { margin: 10px 20px 30px; }       /* top = 10px, left/right = 20px, bottom = 30px */
  .box4 { margin: 10px 20px 30px 40px; }  /* top = 10px, right = 20px, bottom = 30px, left = 40px */
</style>

<div class="box1">margin: 10px</div>
<div class="box2">margin: 10px 20px</div>
<div class="box3">margin: 10px 20px 30px</div>
<div class="box4">margin: 10px 20px 30px 40px</div>
```

[@grant2024] p. 55-58
