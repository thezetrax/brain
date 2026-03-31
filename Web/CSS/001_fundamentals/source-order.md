# Source Order

- If other criteria's are the same, i.e. _same specificity_, _same importance_, the declaration that appears later takes precedence over other declarations
- A declaration might appear later _in the same stylesheet_ or might be appear in a _stylesheet added later in the page_

## Styling Links and Source Order

- When styling _links_, links have state i.e _regular_, _visited_, _hover_ & _active_.
- The order of styling each of these _states_ matters as the _source order_ comes into action
- since the declarations that appear later override other declarations above, order matters when styling _link states_
- When multiple states are active for a _link_, the order of the declarations affects which state is visible to the user
- Simple mnemonic to remember order of link styling _LVHA_ or _LoVe/HAte_ :)

# Example

```html
<!-- Source order matters for link states (LVHA order) -->
<style>
  /* 1. normal state */
  a:link { color: blue; }
  a:visited { color: purple; }
  a:hover { color: green; }
  /* 4. active (clicking) */
  a:active { color: red; }
</style>

<a href="https://example.com">Hover and click me</a>
```

In this order (`link → visited → hover → active`), later declarations override earlier ones when multiple states apply.

[@grant2024] p. 46
