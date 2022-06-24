# Position
*static*
*fixed*
  - relative to viewport, removed from doc flow
*relative*
  - relative to itself
*absolute*
  - relative to closest positioned ancestor, removed from doc flow
*sticky*
  - relative until given offset position is met with viewport then becomes fixed
  - returns to relative when reaches end of content of parent element

inset
top/right/bottom/left

*z-index*
- only affects positioned elements
- stacking context

*overflow*
- controls behaviour when overflows positioned ancestor
- if ancestor is body, set overflow for html as well

*Float*
none left right

# Display
*none*
*inline*
- inline box split across more than one line still one box
- vertical padding, margin, border not respected, height and width not respected (use line-height instead)
*block*
*inline-block*
- vertical padding, margin, border, height and width respected 
- white space in html may cause unexpected behaviour

*visibility: hidden*
*opacity*

*vertical-align*
