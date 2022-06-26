# Fetch
let response = await fetch(url, [options])

*Response properties*
response.status – HTTP code of the response,
response.ok – true if the status is 200-299.
response.headers – Map-like object with HTTP headers.

*Methods to get response body*
response.text() – return the response as text,
response.json() – parse the response as JSON object,
response.formData() – return the response as FormData object (multipart/form-data encoding, see the next chapter),
response.blob() – return the response as Blob (binary data with type),
response.arrayBuffer() – return the response as ArrayBuffer (low-level binary data),

# Formdata
# Fetch Progress
# Fetch Abort

# CORS

# Fetch API
let promise = fetch(url, {
  method: "GET", // POST, PUT, DELETE, etc.
  headers: {
    // the content type header value is usually auto-set
    // depending on the request body
    "Content-Type": "text/plain;charset=UTF-8"
  },
  body: undefined // string, FormData, Blob, BufferSource, or URLSearchParams
  referrer: "about:client", // or "" to send no Referer header,
  // or an url from the current origin
  referrerPolicy: "no-referrer-when-downgrade", // no-referrer, origin, same-origin...
  mode: "cors", // same-origin, no-cors
  credentials: "same-origin", // omit, include
  cache: "default", // no-store, reload, no-cache, force-cache, or only-if-cached
  redirect: "follow", // manual, error
  integrity: "", // a hash, like "sha256-abcdef1234567890"
  keepalive: false, // true
  signal: undefined, // AbortController to abort request
  window: window // null
});

# URL Object
let url = new URL(url, [base])

https://site.com:8080/path/page?p1=v1&p2=v2...#hash

https:            //protocol
site.com:8080     //host
site.com          //hostname
8080              //port

/path/page?p1=v1&p2=v2...#hash    //href
/path/page                        //pathname
?p1=v1&p2=v2...                   //search
#hash                             //hash

*SearchParams*
url.searchParams (object of type URLSearchParams)

- properties:
append(name, value) – add the parameter by name,
delete(name) – remove the parameter by name,
get(name) – get the parameter by name,
getAll(name) – get all parameters with the same name (that’s possible, e.g. ?user=John&user=Pete),
has(name) – check for the existence of the parameter by name,
set(name, value) – set/replace the parameter,
sort() – sort parameters by name, rarely needed,
…and it’s also iterable, similar to Map.

*Encoding*
encodeURI – encodes URL as a whole.
decodeURI – decodes it back.
encodeURIComponent – encodes a URL component, such as a search parameter, or a hash, or a pathname.
decodeURIComponent – decodes it back.

# XMLHttpRequest
# Resumable file upload

# Polling
Regular Polling - request to server every x seconds

Long Polling
1. A request is sent to the server.
2. The server doesn’t close the connection until it has a message to send.
3. When a message appears – the server responds to the request with it.
4. The browser makes a new request immediately.

# WebSocket

# Server Sent Events
let source = new EventSource(url, [credentials]);
- persistent connection, only server sends data, only sends text, regular HTTP Protocol