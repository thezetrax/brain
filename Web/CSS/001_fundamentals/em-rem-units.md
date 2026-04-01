# Ems & Rems

- "em" is "m" and "rem" is "root m"
- Both are relative units that are based on the font size of _an element_
- element referring to _current element_, _parent element_ or _root element_

## Ems

- `em` is a relative unit that is based on the font size of the _current or parent element_
- `1em` is equal to the _font size of the current element_.
- If the current element does not have a specified font size, it inherits the font size from its parent element.
- When setting _font-size_ of an element using `em`, it is based on the _font size of its parent element_.
- Since the element already inherits the base value from the tree
  - We can use a calculation like `font-size: 1.2em` to make the font size 20% larger than the inherited font size.
  - If we have a specific font size in `pixel`, we can use this calculation
  - `value_em = desired_px / parent_size_px`

### Calculations using Ems

When using `Ems` we need a set of formulas for calculating certain values from `ems` to `pixels` and back

- _Find pixel to ems:_ `value_em = desired_px / parent_size_px`
- _Find ems to pixel:_ `value_em * parent_size_px = desired_px`

# Rems

- `Rems` is the exact same as `Ems` but it's always going to refer to the _root element_ of the page
- The root element is defined as `<html>` in HTML and `:root` in CSS

# Note

- When setting `em` unit for font-size 
  - it can lead to compounding effects if multiple nested elements use `em` for their font sizes.
- Using `rem` should be the _**default for setting font-size on elements**_
- Using `em` should be the _**default for setting values for properties except font-size**_
- The process should be `set root font size > set element font size using rem > set other properties using em`
