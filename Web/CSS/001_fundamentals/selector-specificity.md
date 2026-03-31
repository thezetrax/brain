# Selector Specificity

## Question

- Why does a ruleset with an ID selector override a ruleset with a class selector?
- Why do some rulesets override others when they target the same element?

## Definition

- [[css-selectors]] specificity is the _degree of precedence of a ruleset_ determined by the _selector(s)_ of the _ruleset_.
- A ruleset with higher specificity is prioritized by the [[css-cascade]]
- Selector types have different specificities, below they are listed in descending order
  1. ID selector
  2. Class selector
  3. Tag/Type selector
- Rulesets with _more selectors of a selector type_ have higher precedence over other rulesets

## Notes

- Pseudo-class selectors have the same precedence as class selectors.
- Attribute selectors have the same precedence as class selectors.
- Universal selector (`*`) and combinator (e.g., `>`, `+`, `~`, ` `) have no specificity, do not contribute to the specificity calculation.

## Specificity Notation & Calculation

- Specificity can be represented as a three-part value (a, b, c) where:
  - a = number of ID selectors
  - b = number of class selectors, attribute selectors, and pseudo-class selectors
  - c = number of tag/type selectors
- Calculation of specificity is done by counting the number of each type of selector in a ruleset and comparing the values in order 
  - (first a, then b, then c) to determine which ruleset has higher specificity.

## Overriding Specificity Prioritization

Methods for overriding declarations between _rulesets_

- taking caution when setting up specificity in _ruleset_ selectors
  - keep specificity low as much as possible
  - when necessary, increase specificity carefully
  - avoid unnecessarily high specificity, as it can make maintenance difficult and lead to unexpected results
- using `!important` declarations
  - a _ruleset_ having higher specificity can have _declarations overridden_ by a ruleset with lower precedence when having setting declarations as [[important-declarations]]
  - setting the _important_ declaration will set the _declaration_ to higher priority, thus having a higher precedence over the _non-important/normal declaration_
  - important declarations will override normal declarations regardless of their specificity, but important declarations with higher specificity will still take precedence over important declarations with lower specificity.
  - important declarations should be considered a quick hack and not a proper solution to overriding styles. Important declarations should be used sparingly, as they can make debugging and maintenance more difficult.

## Example

```html
<!-- Specificity example:
     ID = 1-0-0
     Class = 0-1-0
     Tag/Type = 0-0-1
-->

<style>
  /* 0-0-1 */
  p { color: gray; }

  /* 0-1-0 */
  .text { color: green; }

  /* 0-2-0 (two class selectors, higher than one class) */
  .text.highlight { color: orange; }

  /* 1-0-0 (ID wins over classes and tags) */
  #main { color: red; }
</style>

<p id="main" class="text highlight">
  This text will be red because the ID selector wins.
</p>
```

[[css-syntax]]
[@grant2024] p. 41
