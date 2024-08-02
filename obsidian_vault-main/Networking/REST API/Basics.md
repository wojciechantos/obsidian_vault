- [[#What is API|What is API]]
- [[#What is REST?|What is REST?]]
- [[#REST API Rules|REST API Rules]]
- [[#Real life examples|Real life examples]]
- [[#Basics of REST|Basics of REST]]
- [[#Status Codes|Status Codes]]
- [[#RESTful API should be Sateless. What does that mean?|RESTful API should be Sateless. What does that mean?]]
- [[#Pagination|Pagination]]
- [[#Versioning|Versioning]]

### What is API
API stands for Application Programming Interface. It is a way for two computers to talk to each other.

### What is REST?
REST stands for REpresentational State Transfer. It is a common API standard used by most mobile and web applications to talk to the servers.
REST is not a specification. It is a loose set of rules that has been the common standard for building the Web APIs since the early 2000's. 

### REST API Rules

- Uniform Interface
- Client-Server
- Stateless
- Cacheable
- Layered System
- Code on Demand (optional)

An API that follows the REST standard is called **RESTful**.

### Real life examples

- Twilio
- Stripe
- Google Maps

---

### Basics of REST

RESTful API organizes resources into a set of unique URIs (Uniform Resource Identifiers - "https://example.com/api/v3/products").
URIs differentiate a different types of resources on a server. 

Example:

![[URI examples 1.png]]

==The resources should be grouped by noun, not verb!==

The client interacts with a resource by making a request to the endpoint for the resource over HTTP. The request has a very specific format, like presented below:

![[URI request line.png]]

The URI is preceded by an HTTP verb which tells the server what we want to do with the resource.

![[URI request line naming.png]]


In a body of these requests there could be an optional HTTP request body that contains a custom payload of data usually encoded in JSON format.

![[HTTPwithBody.png]]

The server receives a request, processess it and formats a result into a response the first line of the response contains HTTP Status Code to tell the client what happened to the request. 

![[HTTPResponseStatusCode.png]]


---
### Status Codes

Well implemented RESTful API returns propper HTTP Status Codes. 

- 200-level - SUCCESS
- 400-level - Something wrong with our request
- 500-level - Something went wrong at the server level


---

### RESTful API should be Sateless. What does that mean?

It means the two parties (ex. client-server) don't need to store any information about each other. Every request and response is independent from all others. This leads to web apps are easy to scale and well behaved.

![[RESTisStateless.png]]

---

### Pagination

If an API endpoint returns a huge amount of data we should use pagination. A common pagination scheme uses limit and offset as parameters . Here is an example:

> /products?limit=25&offset=50

If they are not specified, server shoul assume some sensible default values.

---

### Versioning

Versioning allows an implementation to provide backward compatibility so that if we introduce breaking changes from one version to another, the consumers can get enough time to move to the next version. There are many ways to version an API. The most straight forward is to prefix the version before the resource in a URI:

> /v1/products

