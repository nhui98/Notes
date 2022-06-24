# height 100% issue
- positioned ancestor / html, body needs height defined

# margin: auto
- centres elements for block level elements with an explicitly assigned width
# margin-inline
- only effects left and right

# breaking out of parent container
width: 100vw
margin-inline-start: 50%
transform: translate(-50%)

# Scrolling
scroll-behaviour: smooth;
scroll-padding-top

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

# Scroll-linked Animation
@scroll-timeline timelineName {
  - define where the scroll tracking starts and end
}

- create an animation that links with the scrolling
- set: animation: animationName 1s linear both
- set: animation-timeline: timelineName

(or use js with polyfill)
import "https://flackr.github.io/scroll-timeline/dist/scroll-timeline.js"


