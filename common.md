# What is SOLID?

#### [Single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle)
A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.
#### [Open–closed principle](https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle)
"Software entities ... should be open for extension, but closed for modification."
#### [Liskov substitution principle](https://en.wikipedia.org/wiki/Liskov_substitution_principle)
"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.
#### [Interface segregation principle](https://en.wikipedia.org/wiki/Interface_segregation_principle)
"Many client-specific interfaces are better than one general-purpose interface."[4]
#### [Dependency inversion principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle)
One should "depend upon abstractions, [not] concretions."[4]


# What is REST?

Representational state transfer (REST) is a software architectural style that defines a 
set of constraints to be used for creating Web services.

### RESTful API Design and Architecture Constraints

#### Use of a uniform interface (UI)
Resources should be uniquely identifiable through a single URL, and only by using the underlying methods of the network protocol, such as DELETE, PUT and GET with HTTP, should it be possible to manipulate a resource.

#### Client-server based
There should be a clear delineation between the client and server. UI and request-gathering concerns are the client’s domain. Data access, workload management and security are the server’s domain. This loose coupling of the client and server enables each to be developed and enhanced independent of the other.

#### Stateless operations
All client-server operations should be stateless, and any state management that is required should take place on the client, not the server.

#### RESTful resource caching
All resources should allow caching unless explicitly indicated that caching is not possible.

#### Layered system
REST allows you to use a layered system architecture where you deploy the APIs on server A, and store data on server B and authenticate requests in Server C, for example. A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.

#### Code on demand (optional)
Most of the time a server will send back static representations of resources in the form of XML or JSON. However, when necessary, servers can send executable code to the client.

# HTTP request methods

#### GET
The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.

#### HEAD
The HEAD method asks for a response identical to that of a GET request, but without the response body.

#### POST
The POST method is used to submit an entity to the specified resource, often causing a change in state or side effects on the server.

#### PUT
The PUT method replaces all current representations of the target resource with the request payload.

#### DELETE
The DELETE method deletes the specified resource.

#### CONNECT
The CONNECT method establishes a tunnel to the server identified by the target resource.

#### OPTIONS
The OPTIONS method is used to describe the communication options for the target resource.

#### TRACE
The TRACE method performs a message loop-back test along the path to the target resource.

#### PATCH
The PATCH method is used to apply partial modifications to a resource.

# Idempotent methods 
An idempotent HTTP method is a HTTP method that can be called many times without different outcomes. It would not matter if the method is called only once, or ten times over. The result should be the same. Again, this only applies to the result, not the resource itself. 

| HTTP Method | Idempotent | Safe |
|---|---|---|
| OPTIONS | yes |yes |
| GET | yes | yes |
| HEAD | yes | yes |
| PUT | yes | no |
| POST | no | no |
| DELETE | yes | no |
| PATCH | no | no |

# HTTP Status Codes
**1xx: Informational**	Communicates transfer protocol-level information.

**2xx: Success**	Indicates that the client’s request was accepted successfully.

**3xx: Redirection**	Indicates that the client must take some additional action in order to complete their request.

**4xx: Client Error**	This category of error status codes points the finger at clients.

**5xx: Server Error**	The server takes responsibility for these error status codes.

# Authentication
Authentication is about validating your credentials such as Username/User ID and password to verify your identity. 

#### Single-Factor Authentication
The person can request access to the system using only one of the credentials to verify one’s identity.

#### Two-Factor Authentication
This authentication requires a two- step verification process which not only requires a username and password, but also a piece of information only the user knows.

#### Multi- Factor Authentication
This is the most advanced method of authentication which requires two or more levels of security from independent categories of authentication to grant user access to the system

# Authorization
the process to determine whether the authenticated user has access to the particular resources

# Difference Between HTTP and HTTPS
The primary difference between HTTP and HTTPS protocol is that HTTP is not secure whereas HTTPS is a secure protocol which uses TLS/SSL certificate to ensure the authentication. 

# What is CSRF?
A CSRF token is a unique, secret, unpredictable value that is generated by the server-side application and transmitted to the client in such a way that it is included in a subsequent HTTP request made by the client. When the later request is made, the server-side application validates that the request includes the expected token and rejects the request if the token is missing or invalid.

CSRF tokens can prevent CSRF attacks by making it impossible for an attacker to construct a fully valid HTTP request suitable for feeding to a victim user. Since the attacker cannot determine or predict the value of a user's CSRF token, they cannot construct a request with all the parameters that are necessary for the application to honor the request.

# What is SOAP?
**SOAP** or **Simple Objects Access Protocol** is a web communication protocol designed for Microsoft back in 1998. Today, it’s mostly used to expose web services and transmit data over HTTP/HTTPS. But it’s not limited to them. SOAP, unlike the REST pattern, supports the XML data format only and strongly follows preset standards such as messaging structure, a set of encoding rules, and a convention for providing procedure requests and responses.

# Design Patterns
[https://refactoring.guru/design-patterns](https://refactoring.guru/design-patterns)
