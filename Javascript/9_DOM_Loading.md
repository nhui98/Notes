# HTML page lifecycle
1. DOMContentLoaded – the browser fully loaded HTML, and the DOM tree is built, but external resources like pictures <img> and stylesheets may not yet have loaded.
2. load – not only HTML is loaded, but also all the external resources: images, styles etc.
3. beforeunload/unload – the user is leaving the page.

window.onload
window.onunload
window.onbeforeunload

document.readyState .readystatechange
- "loading" – the document is loading.
- "interactive" – the document was fully read.
- "complete" – the document was fully read and all resources (like images) are loaded too.

# Async & Defer
- downloading of such scripts doesn’t block page rendering.
async	- Load-first order. Their document order doesn’t matter – which loads first runs first
defer	- Document order (as they go in the document).

# Load and Error
load triggers on a successful load
error triggers on a failed load.

To allow cross-origin access, the <script> tag needs to have the crossorigin attribute, plus the remote server must provide special headers.
Three levels of cross-origin access:
1. No crossorigin attribute – access prohibited.
2. crossorigin="anonymous" – access allowed if the server responds with the header Access-Control-Allow-Origin with * or our origin. Browser does not send authorization information and cookies to remote server.
3. crossorigin="use-credentials" – access allowed if the server sends back the header Access-Control-Allow-Origin with our origin and Access-Control-Allow-Credentials: true. Browser sends authorization information and cookies to remote server.

# Mutation Observer 
observes a DOM element and fires a callback when it detects a change.

let observer = new MutationObserver(callback);
observer.observe(node, config);

- config is an object with boolean options “what kind of changes to react on”:
childList – changes in the direct children of node
subtree – in all descendants of node
attributes – attributes of node
attributeFilter – an array of attribute names, to observe only selected ones.
characterData – whether to observe node.data (text content)
attributeOldValue – if true, pass both the old and the new value of attribute to callback (see below), otherwise only the new one (needs attributes option),
characterDataOldValue – if true, pass both the old and the new value of node.data to callback (see below), otherwise only the new one (needs characterData option).

observer.disconnect() – stops the observation.
observer.takeRecords() – gets a list of unprocessed mutation records – those that happened, but the callback has not handled them.

*MutationRecord object*
- first argument passed to the callback
type – mutation type, one of
  "attributes": attribute modified
  "characterData": data modified, used for text nodes,
  "childList": child elements added/removed,
target – where the change occurred: an element for "attributes", or text node for "characterData", or an element for a "childList" mutation,
addedNodes/removedNodes – nodes that were added/removed,
previousSibling/nextSibling – the previous and next sibling to added/removed nodes,
attributeName/attributeNamespace – the name/namespace (for XML) of the changed attribute,
oldValue – the previous value, only for attribute or text changes, if the corresponding option is set attributeOldValue/characterDataOldValue.