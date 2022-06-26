# Events
*mouse events*
click                 //when the mouse clicks on an element (touchscreen devices generate it on a tap).
contextmenu           //when the mouse right-clicks on an element.
mouseover/mouseout    //when the mouse cursor comes over / leaves an element.
mousedown/mouseup     //when the mouse button is pressed / released over an element.
mousemove             //when the mouse is moved.
*keyboard events*
keydown/keyup         //when a keyboard key is pressed and released.
*form element events*
submit                //when the visitor submits a <form>.
focus                 //when the visitor focuses on an element, e.g. on an <input>.
*Document events*
DOMContentLoaded      //when the HTML is loaded and processed, DOM is fully built.
*CSS events*
transitionend         //when a CSS-animation finishes.

*adding event listeners*
1. HTML attribute: onclick="...".
2. DOM property: elem.onclick = function.
3. Methods: elem.addEventListener(event, handler[, phase]) to add, removeEventListener to remove.

# Event Bubbling + Capturing
When an event happens – the most nested element where it happens gets labeled as the “target element” (event.target)
Then:
1. Event moves down from doucment root to event.target, triggering all event listeners with: addEventListener(..., {capture: true})
2. Handlers called on target element itself
3. Event bubbles up from event.target to root, calling handlers

Each handler has access to event obj properties
- event.target – the deepest element that originated the event.
- event.currentTarget (=this) – the current element that handles the event (the one that has the handler on it)
- event.eventPhase – the current phase (capturing=1, target=2, bubbling=3).

event.stopPropagation()             //stops bubbling
event.stopImmediatePropagation()    //stops bubbling and prevents other handlers attached to current element to run

# Event Delegation
Put a single handler on common ancestor instead of assigning a handler to each element
- In the handler – check the source element event.target
- If the event happened inside an element that interests us, then handle the event.

*Default Browser Actions*
event.preventDefault() or return false

passive: true option of addEventListener
- tells the browser that the action is not going to be prevented
- true by default in some browsers and improves performance

# Custom Events
let event = new Event(type, options?)     //better to use an existing UI Event or CustomEvent and set additional option: detail
- type – event type, a string like "click" or our own like "my-event".
- options: //default {bubbles: false, cancelable: false}
bubbles: true/false 
cancelable: true/false – if true, then the “default action” may be prevented.

elem.dispatchEvent(event);

# Mouse Events
mousedown/mouseup     //Mouse button is clicked/released over an element.
mouseover/mouseout    //Mouse pointer comes over/out from an element.
mousemove             //Every mouse move over an element triggers that event.
click                 //Triggers after mousedown and then mouseup over the same element if the left mouse button was used.
dblclick              //Triggers after two clicks on the same element within a short timeframe. Rarely used nowadays.
contextmenu           //Triggers when the right mouse button is pressed.

mouse events have additional properties:
- button
- altKey, ctrlKey, shiftKey and metaKey (Mac).

Window-relative coordinates: clientX/clientY.
Document-relative coordinates: pageX/pageY.

# Mouse Moving
mouseover
- event.target – is the element where the mouse came over.
- event.relatedTarget – is the element from which the mouse came (relatedTarget → target).
mouseout 
- event.target – is the element that the mouse left.
- event.relatedTarget – is the new under-the-pointer element, that mouse left for (target → relatedTarget).

mousemove
mouseenter/mouseleave

# Drag n Drop
1. On mousedown – prepare the element for moving, if needed (maybe create a clone of it, add a class to it or whatever).
2. Then on mousemove move it by changing left/top with position:absolute.
3. On mouseup – perform all actions related to finishing the drag’n’drop.
(don’t forget to cancel native ondragstart).
- At the drag start – remember the initial shift of the pointer relative to the element: shiftX/shiftY and keep it during the dragging.
- Detect droppable elements under the pointer using document.elementFromPoint.

# Pointer Events
Pointer event	        Similar mouse event
pointerdown	          mousedown
pointerup	            mouseup
pointermove	          mousemove
pointerover	          mouseover
pointerout	          mouseout
pointerenter	        mouseenter
pointerleave	        mouseleave
pointercancel	        -
gotpointercapture	    -
lostpointercapture    -

- Pointer events allow handling mouse, touch and pen events simultaneously

Additional abilities of pointer events are:
- Multi-touch support using pointerId and isPrimary.
- Device-specific properties, such as pressure, width/height, and others.
- Pointer capturing: we can retarget all pointer events to a specific element until pointerup/pointercancel.

# Keyboard
keydown – on pressing the key (auto-repeats if the key is pressed for long),
keyup – on releasing the key.

Properties:
code – the “key code” ("KeyA", "ArrowLeft" and so on), specific to the physical location of the key on keyboard.
key – the character ("A", "a" and so on), for non-character keys, such as Esc, usually has the same value as code.

# Scrolling
scroll

# Form Element
document.forms document.forms[name/index]
form.elements form.elements[name/index]
element.form

input.value textarea.value select.value input.checked
select.selectedIndex select.options

# Focus, Blur
Events focus and blur trigger on an element focusing/losing focus.
- They do not bubble. Can use capturing state instead or focusin/focusout.
- Most elements do not support focus by default. Use tabindex to make anything focusable.
The current focused element is available as document.activeElement.

# Change Input
change - A value was changed.	For text inputs triggers on focus loss.
input -	For text inputs on every change.	Triggers immediately unlike change.
cut/copy/paste - The action can be prevented. The event.clipboardData property gives access to the clipboard.

# Form Submit
submit
form.submit()

# Selection, Range
For document: Selection and Range objects.
For input, textarea: additional methods and properties.
