# Progressive Enhancement

- CSS is designed to be **progressive**, meaning it's _backwards_ and _forwards_ compatible
- This feature of CSS, and HTML, is known as _**resilience**_.
  - Older browsers will ignore CSS they don't understand
  - Newer browsers can take advantage of new features without breaking the page
- Both **HTML & CSS** are designed to be fault tolerant
- Progressive enhancement can be achieved through the use of the cascade, selectors, and [[css-supports-rules]]

## Using Cascade for Progressive Enhancement

- [[css-cascade]] is a powerful tool for progressive enhancement
- You can write CSS that applies to all browsers, and then add more specific rules for newer browsers
- This allows you to provide a basic experience for all users, while enhancing the experience for those with modern browsers

## Progressively Enhancing Selectors

- [[css-selectors]] have evolved to include powerful features, like `:has()`, which allows you to select elements based on their children
- You can use `@supports` to check if the browser supports a specific selector, and then apply styles accordingly
- You can also add the declarations as you would normally, the browser simply ignores it
- However, when adding the selectors you need to ensure the latest selectors have their own separate block to avoid the browser ignoring the entire _ruleset_ if the ruleset contains multiple selectors
- When using the latest selectors, have a separate block for the latest selector to ensure that older browsers _don't ignore the entire ruleset_

## Example (CSS Selector Enhancements)

```css
/* (Might be Ignored) If the browser doesn't support :user-invalid */
input.invalid,
input:user-invalid {
  border-color: red;    
}

input.invalid {
  border-color: red;    
}
/* Enhanced styling for browsers that support :user-invalid */
input:user-invalid {
  border-color: red;    
}
```

## Example (Basic Cascade Usage)

```html
<style>
  .panel {
    /* Fallback for older browsers */
    width: 50%;
    /* Enhanced for browsers that support container query units */
    width: 50cqw; /* 50% of the container’s width */
  }
</style>

<div class="panel">
  This panel uses <code>cqw</code> (container query width) if supported,
  otherwise it falls back to <code>90%</code> / <code>max-width</code>.
</div>
```

[@grant2024] p. 59-64
