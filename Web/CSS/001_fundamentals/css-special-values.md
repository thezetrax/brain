# CSS Special Values

- **special values** are keywords that can be used to manipulate the [[css-cascade]].
- Special values can still be overridden by other _rulesets_ with _higher precedence_, but they provide a way to control the behavior of properties in specific ways.
- There are four special values that can be used in CSS:
  1. `inherit`: This value causes a property to _inherit_ the property when a [[cascaded-value]] is preventing inheritance. For example, if you set `color: inherit;` on a child element, it will take the color of its parent.
  2. `initial`: This value resets a property to its default value as defined by the CSS specification. For example, if you set `color: initial;`, it will reset the color to the default (usually black).
  3. `unset`: This value acts as either `inherit` or `initial`, depending on whether the property is naturally inherited or not. If the property is normally inherited, it behaves like `inherit` otherwise, it behaves like `initial`.
  4. `revert`: This value resets a property to the value established by the user-agent stylesheet (the browser's default styles) or by any user stylesheets, effectively undoing any changes made by author stylesheets.

## Initial Value

- The initial value is used as a hard reset for a property
- Useful when you want to ensure that a property is set to its default state
- The proper way to reset a property, such as `width`, is to use the `initial` value, which will reset it to its default value of `auto`
- Using `width: auto` is not the same as `width: initial` because `auto` is not the default value for all elements, while `initial` will reset it to the default value defined by the CSS specification.
- `initial` resets a _property to it's default value_, **regardless** of the element it's applied to.
- When setting `display: initial` to a element, it will set the value to `inline` regardless of the element, `<div>` or `<span>`, because the _default value_ of the `display` property is `inline`.

## Revert Value

- The `revert` value is used to reset a property to the value established by the user-agent [[stylesheet-origin]] (the browser's default styles) effectively undoing any changes made by author stylesheets.
- This can be useful when you want to remove any custom styles applied to an element and revert it back to the default styling provided by the browser and not necessarily _the default value of the property_ unlike `initial`.
- Setting a `<div>` element to `display: revert` will reset the display property to `block`, which is the default value for a `<div>` element in the user-agent stylesheet, while setting a `<span>` element to `display: revert` will reset the display property to `inline`, which is the default value for a `<span>` element in the user-agent stylesheet.

## Example

```html
<style>
  body {
    color: navy;
    font-family: Arial, sans-serif;
  }

  .parent {
    color: darkgreen;
    border: 2px solid black;
    padding: 8px;
  }

  .inherit { color: inherit; }      /* gets darkgreen from .parent */
  .initial { color: initial; }      /* resets to default (usually black) */
  .unset   { color: unset; }        /* color is inherited → behaves like inherit */
  .revert  { color: revert; }       /* back to browser/user default color */

  .box {
    display: inline-block;
    padding: 4px;
    margin: 4px;
  }

  .initialDisplay { display: initial; } /* display becomes inline (property default) */
  .revertDisplay  { display: revert; }  /* display becomes block for div (User-Agent default) */
</style>

<div class="parent">
  <p class="box inherit">inherit (darkgreen)</p>
  <p class="box initial">initial (default black)</p>
  <p class="box unset">unset (inherits darkgreen)</p>
  <p class="box revert">revert (browser default)</p>
</div>

<div class="box initialDisplay">display: initial (inline)</div>
<div class="box revertDisplay">display: revert (block)</div>
```

[@grant2024] p. 51-55
