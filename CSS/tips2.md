# Simple Color Scheme
Black + White + Grey + 1 pop color

# Remove specificity
:where(selector) {} //strips the specificity of this selector

# Background image
background-color //act as a fallback
background-image: url()
background-size: cover
// try not to set a height, instead use padding top and bottom

- cannot change opacity of bg image instead: background-blend-mode: multiply | lighten
- this blends the bg color with the image

# Use hsl() more

# Lazy Loading
<img loading="lazy">

# Backdrop for <dialog>
::backdrop {}
- to open dialog listen for click event and use .showModal() .close()

# Select range of content
:nth-of-child(n+3):nth-of-child(-n+5)
- gets the 3rd to 5th items

# display: contents
- removes the boxes, causing child elements to behave as if these parents dont exist
- removing the boxes means some styles (e.g. bg) cant be applied to the child elements

# Fixing overlapping elements, each with its own shadow
filter: drop-shadow()
- apply on parent element 

# outline for text
-webkit-text-stroke

# scrollsnapping
scroll-snap-type
scroll-snap-align
scroll-padding-inline

# background-repeat: space
- repeats image but contains and evenly spaces it

# console log for css
* {
  - set an outline for all elements
  - set a bg for all elements
}