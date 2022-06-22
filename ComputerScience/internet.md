*IP Address*
- each computer connected to the internet is identified by an Ip Address
*Domain Names*
- readable name for the ip address
*Domain Name System (DNS)*
- mapper between Domain Name and the Ip Address

*(Web)Hosting*
- online service that provides storage and computing resources for the accomodation and maintenance of your website files

*Internet Protocol*
- set of rules governing the format of data sent over the internet

# HTTP
*Hyper Text Transfer Protocol (HTTP)*
- Uses hyperlinks to load websites
- Each request is independant and stateless
*Hyper Text Transfer Protocol Secure (HTTPs)*
- data sent is encrypted using ssl/tls
- these certificates need to be installed on the webhost
*HTTP/2*
- http 1 uses 1 tcp connection and sends files one at a time
- http2 enables full request and response multiplexing, and compression of messages
- faster, less latency, more efficient, more secure

*HTTP Headers*
* General
- request url, request method, status code, remote address, referrer policy
* Response Headers
- Server, Set-Cookie, Content-Type, Content-Length, Date, more...
* Request Headers
- Cookies, Accept-xxx, Content-Type, Content-Length, Authorization, User-Agent, Referrer, more...

*HTTP Methods*
GET - retrieve data from server
POST - submit data to server
PUT - update data already on server
DELETE - delete data on server

*HTTP Status Codes*
1xx Informational
2xx Success
- 200 ok 
- 201 ok created
3xx Redirect
- 301 moved to new url
- 304 not modified (cached version)
4xx Client Error
- 400 bad request
- 401 unauthorized
- 404 not found
5xx Server Error
- 500 internal server error