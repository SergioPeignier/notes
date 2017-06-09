# HTTP tutorial
## Definition
+ The HTTP protocol is a request/response protocol based on the client/server based architecture.
+ Messages encoded in TCP/IP

### Client
+ The HTTP client: sends a request
+ Request: request method, URI, and protocol version, followed by a MIME-like message
+ message: request modifiers, client information, and possible body content over a TCP/IP connection.

### Server
+ HTTP server: responds with a status line
+ Status line: message's protocol version and a success or error code, followed by a MIME-like message
+ message: server information, entity meta information, and possible entity-body content.

## Protocol parameters
### Version
+ HTTP uses a <major>.<minor> numbering: versions of the protocol.
`HTTP-Version   = "HTTP" "/" 1*DIGIT "." 1*DIGIT`
### Uniform Resource Identifiers (URI)
+ URI: formatted, case-insensitive string containing name, location,
`URI = "http:" "//" host [ ":" port ] [ abs_path [ "?" query ]]`
+ Empty port => port 80 assumed
+ Empty abs_path <=> abs_path of "/". 
+ Other characters <=> to their ""%" HEX HEX" encoding.
### Time stamps
+ date/time represented in Greenwich Mean Time:

`Sun, 06 Nov 1994 08:49:37 GMT  ; RFC 822, updated by RFC 1123`
`Sunday, 06-Nov-94 08:49:37 GMT ; RFC 850, obsoleted by RFC 1036`
`Sun Nov  6 08:49:37 1994       ; ANSI C's asctime() format`
### Character sets
+ Character sets the client prefers separated by commas. 
+ Default:  US-ASCII.
### Content Encodings
+ Content encoding:  algorithm used to encode the content before transfer.
+ Content-coding values: case-insensitive.
`Accept-encoding: gzip`
### Media type
+ Media Types used in Content-Type
+ Accept header fields 
+ Goal: provide open and extensible data typing and type negotiation.
`media-type     = type "/" subtype *(";" parameter)`
: The type, subtype, parameter attribute names: case--insensitive.
`Accept: image/gif`
### Language Tags
+ Language tags parts: a primary language tag and a possibly empty series of subtags:
`language-tag  = primary-tag *( "-" subtag )`
`en-US`
## Messages
+ URI to identify a given resource and to establish a connection.
+ Once the connection is established, HTTP messages are passed in a format similar to MIME.
+ Messages: client requests and server responses 
+ Format:
 `HTTP-message   = <Request> | <Response> ; HTTP/1.1 messages`
### Format of Request and Response
+ Generic message format of RFC :
	+ start-line
	+ header file
	+ empty line with `\n`
	+ message body
#### Message Start-Line
+ Generic syntax:
`start-line = Request-Line | Status-Line`

`GET /hello.htm HTTP/1.1     (This is Request-Line sent by the client)`
`HTTP/1.1 200 OK             (This is Status-Line sent by the server)`

### Header Fields
+ Information about request or response or object sent in the message body. 
+ 4 types:
	+ General-header: Applicability for request and response messages.
	+ Request-header: Applicability only for request messages.
	+ Response-header: Applicability only for response messages.
	+ Entity-header: Define meta information about the entity-body or, if no body is present, about the resource identified by the request.
+ Generic format:

`name (:) field value`
`User-Agent: curl/7.16.3 libcurl/7.16.3 OpenSSL/0.9.7l zlib/1.2.3
Content-Type: text/plain`

### Message Body
+ Optional 
+ Carries 
	+ HTTP request data (e.g., form data)
	+ HTTP response data from the server (e.g., files).
`<html>
   <body>  
      <h1>Hello, World!</h1>
   </body>
</html>`

## Requests
+ Request Message set by client.  
### Start line -> Request line
Request-Line = Method SP Request-URI SP HTTP-Version CRLF
#### Method 
+ Method to be performed on the resource identified by Request-URI. 
+ Value: case-sensitive always in uppercase
+ GET, POST ...
#### URI
`Request-URI = "*" | absoluteURI | abs_path | authority`
+ `*` : HTTP request does not apply to a particular resource, but to server itself
+ absoluteURI: HTTP request is being made to a proxy. 
`GET http://www.w3.org/pub/WWW/TheProject.html HTTP/1.1`
+ authority: identify a resource on an origin server or gateway (absolute path has at leat "/").
`GET /pub/WWW/TheProject.html HTTP/1.1`
#### Request-Header
+ Pass additional information about the request, and client itself.
+ Act as request modifiers.

