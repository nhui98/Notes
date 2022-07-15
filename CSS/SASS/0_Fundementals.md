# Setup
npm i -D sass
sass input.scss output.css | sass --watch folder:outfolder

# Imports
_filename.scss                      //partials intended to be imported 
filename.scss                       //files that import partials and are turned into css files

*@Use*
@use <url>
- loads mixins functions and variables from another stylesheet
- access with <namespace>.<variable> | <namespace>.<function>() | <namespace>.<mixin>()
- namespace is just the last component of its url without a file extension
- use as to change  eg. @use <url> as <namespace>

*@Forward*
@forward <url>
@forward <url> as <prefix>-*
@forward <url> hide <members...> | show <members...>

# Variables
$variable-name: value               //global or local scope
$variable-name: value !default      //use the value unless the variable has been set elsewhere

# Nesting
- nest selectors
- nest properties with the same prefix
- & parent selector

# Interpolation
#{}                                 //embed the result of a sassscript expression into a chunk of CSS

# Flow control
@if <expression> {}
@else if<expression> {}
@else {}

@each <variable> in <expression> {}

@for <variable> from <expression> to <expression> {}
@for <variable> from <expression> through <expression> {}

@while <expression> {}

# List / Maps
- Lists (<expression>,) or [<expression>]
- Maps (<expression>: <expression>,)

