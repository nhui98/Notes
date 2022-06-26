# DOM Tree
- every HTML tag is an object, nested tags are children, text inside tag is an object
- everything in html becomes part of the dom as a node

node types:
1. document
2. element nodes
3. text nodes
4. comments

# Navigation
<html> = document.documentElement
<head> = document.head
<body> = document.body

*Children*
.childNodes 
.firstChild .lastChild  

- DOM collections are read only and live
- use for...of to loop over collections

*Parent and Sibling*
.parentNode
.nextSibling .previousSibling

*Element Node Only Navigation*
children 
firstElementChild firstElementChild
parentElement
previousElementSibling nextElementSibling 

*More Links*
Some types of DOM elements, e.g. tables, provide additional properties and collections to access their content.

# Searching
document.getElementById() .getElementsByClassName() .getElementsByTagName() .getElementsByName

elem.querySelector(css) .querySelectorAll(css) 

elem.closest(css) .matches(css)
elemA.contains(elemB)

# Node Properties
*DOM node classes*
EventTarget, Node, Document, CharacterData, Element, HTMLElement

*HTML Element*
basic class for all HTML elements
- HTMLInputElement – the class for <input> elements
- HTMLBodyElement – the class for <body> elements
- HTMLAnchorElement – the class for <a> elements
- and so on...

*Properties*
nodeType
nodeName/tagName
innerHTML
outerHTML
nodeValue/data
textContent
hidden

DOM nodes have other properties depending on their class

# Attributes and properties
*HTML Attributes*
elem.hasAttribute(name)
elem.getAttribute(name)
elem.setAttribute(name, value)
elem.removeAttribute(name)
elem.attributes

*dataset*
<div data-some-name="something">
.dataset.someName

# Modifying the document
*create element*
document.createElement(tag) – creates an element with the given tag,
document.createTextNode(value) – creates a text node (rarely used),
elem.cloneNode(deep) – clones the element, if deep==true then with all descendants.

*inserting*
node.append(...nodes or strings) – append nodes or strings at the end of node,
node.prepend(...nodes or strings) – insert nodes or strings at the beginning of node,
node.before(...nodes or strings) –- insert nodes or strings before node,
node.after(...nodes or strings) –- insert nodes or strings after node,
node.replaceWith(...nodes or strings) –- replaces node with the given nodes or strings.

elem.insertAdjacentHTML(where, html)
where:
"beforebegin" – insert html right before elem,
"afterbegin" – insert html into elem, at the beginning,
"beforeend" – insert html into elem, at the end,
"afterend" – insert html right after elem.

*delete*
node.remove()

# Styles and Classes
className 
classList       //object with methods add/remove/toggle/contains

style           //object with camelCased styles
style.cssText   //corresponds to the whole "style" attribute, the full string of styles

- To read the resolved styles (with respect to all classes, after all CSS is applied and final values are calculated):
getComputedStyle(elem, [pseudo])  //returns the style-like object with them. Read-only.


# Element Size and Scrolling
offsetParent          //nearest ancestor that the browser uses for calculating coordinates during rendering
offsetLeft/offsetTop  //provide x/y coordinates relative to offsetParent upper-left corner.

offsetWidth/Height    //full size including borders
clientWidth/Height    //content + padding (no scrollbar)
clientTop/Left        //border height and width + scrollbar

scrollWidth/Height    //full inner width/height of content area including scrolled out parts
scrollLeft/scrollTop  //scrolled out part of the element ie. how much it scrolled
                      //only non read-only property - can be changed and browser will scroll the element

//for safari
document.body.scrollTop/Left 

# Window Size and Scrolling
window.innerWidth/innerHeight                       //full window width
document.documentElement.clientWidth/clientHeight   //window width no scrollbar

*Width/height of the document*
Math.max(
  document.body.scrollHeight, document.documentElement.scrollHeight,
  document.body.offsetHeight, document.documentElement.offsetHeight,
  document.body.clientHeight, document.documentElement.clientHeight
);

*Scroll*
window.scrollX/scrollY | window.pageYOffset/pageXOffset

scrollBy(x,y)
scrollTo(pageX,pageY)
elem.scrollIntoView(top)

document.body.style.overflow = "hidden"   //forbid scrolling

# Coordinates
elem.getBoundingClientRect() //gets x/y, width/height, top/bottom, left/right

Any point on the page has coordinates:
- relative to window: similar to position: fixed
- relative to the document: similar to position: absolute