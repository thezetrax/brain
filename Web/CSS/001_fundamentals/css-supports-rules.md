# @Supports At-Rule

- At-rules are [[css-syntax]] constructs that provide instructions to the browsers CSS parser
- `@supports` is an at-rule that allows you to apply styles conditionally based on the browser's support for specific CSS features
- `@supports` rule is followed by a declaration, in parentheses, that tests for the support of a particular CSS feature
- If the browser supports the feature being tested, the styles within the `@supports` block

## Feature Queries

- `@supports` is also known as a **feature query** because it allows you to query the browser for support of specific CSS features
- There are multiple ways to write the declaration for the feature query:
  - `@supports (property: value)` checks if the browser supports a specific property-value pair, such as `@supports (display: grid)`
  - `@supports (selector(<feature-here>))` checks if the browser supports a specific selector, such as `@supports selector(:user-invalid)`
  - You can also use logical operators like `and`, `or`, and `not` to combine multiple feature queries, such as 
    - `@supports (display: grid) and (gap: 1rem)`
    - `@supports (display: grid) or (display: flex)`
    - `@supports not (display: grid)`

## Example (Using @supports)

```html
<style>
  /* Basic styling for all browsers */
  .card {
    padding: 1rem;
    border: 1px solid #ccc;
    border-radius: 8px;
  }

  /* Enhanced styling for browsers that support :has() */
  @supports selector(.card:has(img)) {
    .card:has(img) {
      border-color: #4f46e5;
      box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.2);
    }
  }
</style>

<div class="card">
  <h2>Title only</h2>
</div>

<div class="card">
  <img src="thumb.jpg" alt="" />
  <h2>Card with image</h2>
</div>
```
