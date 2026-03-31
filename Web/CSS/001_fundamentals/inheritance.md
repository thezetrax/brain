# CSS Inheritance

- **inheritance** is a mechanism by which some CSS properties are passed down from parent elements to their children
- If an element has no [[cascaded-value]], it may inherit the value from its parent element
- No all properties are inherited by default, but you can explicitly specify that a property should be inherited using the `inherit` keyword
- we don't want a div passing down `border` styling to its children
- Some properties that are commonly inherited include:
  - `color`
  - `font-family`
  - `font-size`
  - `line-height`
  - `text-align`
  - `visibility`
- _inherited properties_ will cascade down the DOM tree, all the descendant elements will inherit the values until it's overridden by a [[cascaded-value]]
- [[chrome-devtools]] can be used to inspect the computed styles of an element and see which properties are inherited and which are not.
- Two main [[css-special-values]] are used to control inheritance:
  1. Use the `inherit` keyword to explicitly specify that a property should be inherited from its parent element.
  2. Use the `initial` keyword to reset a property to its default value, which can prevent inheritance from taking place.

## Example

```html
<!-- Inheritance example using <body> -->
<!-- Every element inside the `<body>` will inherit the `color`, `font-family`, and `font-size` properties, but not the `border` property, which is not inherited by default. The `<span>` element explicitly inherits the border from its parent using the `inherit` keyword. -->
<style>
  body {
    color: darkblue;
    font-family: Arial, sans-serif;
    font-size: 18px;
    border: 2px solid black; /* NOT inherited */
  }
  
  span {
    border: inherit; /* Explicitly inherit the border from the parent */
  }
</style>

<body>
  <p>This paragraph inherits color and font settings from <code>body</code>.</p>
  <p>
    <span>This span explicitly inherits the parent's color.</span>
  </p>
</body>
```

[@grant2024] p. 50
