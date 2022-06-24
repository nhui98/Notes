# Box Model
content - padding - border - margin

# Box Sizing
- include padding and border in height and width 
box-sizing: border box 

# Specificity + Cascade
- higher specificity wins
- if same specificity, most recent applied style wins

# Custom Variables
:root {
  --globalVar: value
}
--scopedVar: value

var(--globalVar, //fallback?)

# Media Queries
@media (min-width | max-width) {}

# Units & Sizing
*px*

*%*
- relative to viewport if positioned fixed
- relative to closest positioned ancestor if positioned absolute
- relative to closest block ancestor if relative/static

*em*
- on font-size is relative to parent font size
- on other property is relative to own font size

*rem*
- relative to root/html font size

*vw vh vmin vmax*

*min-width/height*
*max-width/height*