# CSS & Browser Support
- caniuse
- autoprefixer
- @support (property) {}
- polyfills

# Reset Styles
list-style

# Outline
outline
outline-offset

# outline for text
-webkit-text-stroke

# Math Functions
calc() min() max()

# Pointer Events
pointer-events

# Fluid type scale
https://utopia.fyi/

# Scrolling
scroll-behaviour: smooth;
scroll-padding-top

# margin
margin: auto  //centres elements for block level elements with an explicitly assigned width
margin-inline //only effects left and right

# Lazy Loading
<img loading="lazy">

# Scroll-linked Animation
@scroll-timeline timelineName {
  - define where the scroll tracking starts and end
}

- create an animation that links with the scrolling
- set: animation: animationName 1s linear both
- set: animation-timeline: timelineName

(or use js with polyfill)
import "https://flackr.github.io/scroll-timeline/dist/scroll-timeline.js"\

# scrollsnapping
scroll-snap-type
scroll-snap-align
scroll-padding-inline

