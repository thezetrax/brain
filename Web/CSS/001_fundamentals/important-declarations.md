# Important Declarations

- Important declaration have higher priority compared to _normal_, non-important, declarations.

# Example

```html
<style>
  /* Lower specificity, but marked as important */
  .notice {
    color: blue !important;
  }

  /* Higher specificity, but normal declaration */
  #message {
    color: red;
  }
</style>

<p id="message" class="notice">
  This text will be blue.
</p>
```

[@grant2024] p. 40
