# CSS Units

- CSS units are divided into two categories: _absolute_ and _relative_ units.
- _Absolute unit_ values are _fixed_. `5px` always means the same value.
- _Relative unit_ values _changes based on the context_. `5em` can mean different values depending on the font size of the element.
- Length denotes a measure of distance in css
- Percentage is a relative unit but not a length unit

# Relative Units

- Also known as _computed values_
- Values declared using relative units are evaluated at runtime, when rendered
- When evaluated the value is calculated to a fixed, _absolute value_
- The need for relative units arises because the web environment is dynamic by default
- Users device or browser settings and configuration are impossible to predict, and the content of a page can change dynamically.
  - Browser zoom, font size, and window size can all change
  - User's screen configuration, and settings are always different from one another
- _relative units_ are the primary tool for creating [[css-responsive-design]] and [[css-accessibility]]
- Modern & common relative units are
  - [[em-rem-units]] relative units based on font size
  - [[viewport-units]] relative units based on viewport size
  - [[percentage-units]]

[@grant2024] p. 65
