# height 100% issue
- positioned ancestor / html, body needs height defined

# breaking out of parent container
width: 100vw
margin-inline-start: 50%
transform: translate(-50%)

*fixed navigation covering content*
- use a custom property value for scroll-padding-top
- get .offsetHeight of content element and set document.documentElement.style.setProperty('--custom-property', offsetHeight - 1 + "px")

# Create Blobs with border radius
border-radius: tleft-value tright-value bright-value bleft-value / tleft-value2 tright-value2 bright-value2 bleft-value2
(or)
border-top-left-radius: value1 value2
...

# Hover on mobile
@media (hover: hover) {
  <!-- target only devices that support hover -->
  - add hover styles here
  - non hoverable devices should just show the hovered state
}

# console log for css
* {
  - set an outline for all elements
  - set a bg for all elements
}

# Remove specificity
:where(selector) {} //strips the specificity of this selector

# Fixing overlapping elements, each with its own shadow
filter: drop-shadow()
- apply on parent element 

# Backdrop for <dialog>
::backdrop {}
- to open dialog listen for click event and use .showModal() .close()