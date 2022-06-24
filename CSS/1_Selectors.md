# Selectors
*Attribute Selectors*
[attr]
[attr=value]
[attr~=value] *contains value*
[attr*=value] *contains substring value*
[attr|=value] *equal to value or starts with value*
[attr^=value] *starts with*
[attr$=value] *ends with value*

*Combinators*
(space)   descendant
>         child
+         adjacent sibling
~         general sibling

*Pseudo class*
:hover :focus :not(selector)
:first/last-child :nth-child(n) :only-child 
:first/last-of-type :nth-of-type(n) :only-of-type

:empty
- targets if content is empty (white space counts as content)
:target {}

*Pseudo Element*
::before ::after

# Select range of content
:nth-of-child(n+3):nth-of-child(-n+5)
- gets the 3rd to 5th items