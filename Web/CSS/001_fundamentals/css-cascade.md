# The Cascade

- **cascade** is a rules that determine the precedence of _rulesets_ for a _select element_
- **cascade** determines how conflicts are resolved when a conflicting style is applied to an element(s)
- These rules allow browsers to behave predictably when resolving ambiguity in CSS
- [[cascade-resolution-criteria]] are cascade rules that determine how conflicts are resolved
- A declaration that wins the precedence is called a [[cascaded-value]]

## Rules of Thumb

- Don't(s) when writing _rulesets_
  1. Don't use IDs in css selectors
  2. Don't use `!important` declarations
- If you're distributing a _JavaScript library_, e.g. through npm, **don't style elements using [[inline-styles]]**
  - the only way users of your library are able to change the styling is by using `!important` declarations
  - instead use a stylesheet within your library


[@grant2024] p. 35
