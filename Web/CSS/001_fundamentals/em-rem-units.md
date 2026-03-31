# Ems & Rems

- abbreviation of "em" is "m" and "rem" is "r"
- Both are relative units that are based on the font size of an _element_
- element referring to _current element_, _parent element_ or _root element_

# Ems

- `em` is a relative unit that is based on the font size of the _current or parent element_
- `1em` is equal to the _font size of the current element_.
- If the current element does not have a specified font size, it inherits the font size from its parent element.
- When setting _font-size_ of an element using `em`, it is based on the font size of its parent element.
- This can lead to compounding effects if multiple nested elements use `em` for their font sizes.
