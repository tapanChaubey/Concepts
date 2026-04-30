# REST Architecture and REST API Concepts

## Introduction
REST (Representational State Transfer) is an architectural style used to design web services.  
It is commonly used for building APIs that allow communication between different systems over the internet. REST is simple, l
ightweight, and works mainly over HTTP protocol. It focuses on resources and how they are accessed using standard methods.

## Key Principles of REST Architecture
1. Stateless
In REST, every request from the client must contain all the required information.
The server does not store any session or client data between requests. This makes the system more scalable and reliable.

3. Client Server Architecture
The client and server are independent of each other. The client handles the user interface,
while the server manages data and business logic. This separation improves flexibility and allows both sides to be developed independently.

3. Uniform Interface
REST APIs follow a standard way of communication. This includes using HTTP methods,
consistent URI structure, and standard response formats like JSON. This makes APIs easy to understand and use.

5. Cacheable
Responses from the server can be stored or cached by the client.
This reduces the number of requests sent to the server and improves performance.

7. Layered System
REST allows multiple layers between client and server, such as security layers,
load balancers, and proxies. The client does not need to know about these layers.

HTTP Methods in Detail
* GET
Used to fetch data from the server. It is safe and idempotent, 
which means it does not change server state and can be called multiple times without side effects.
Example :  @GetMapping("/users")
       public List<User> getAllUsers() {
        return userService.getAllUsers();
         }

* POST
Used to create a new resource. It is not idempotent, 
meaning repeated requests can create multiple resources.
Example : @PostMapping("/users")
        public User createUser(@RequestBody User user) {
         return userService.saveUser(user);
         }

* PUT
Used to completely update an existing resource. 
It is idempotent because repeated requests result in the same state.

* PATCH
Used to partially update a resource. 
It modifies only specific fields instead of replacing the entire resource.

* DELETE
Used to remove a resource. 
It is idempotent because deleting the same resource multiple times gives the same result.

## Idempotency in REST
Idempotency means that performing the same operation multiple times results in the same outcome.
For example, calling a DELETE request multiple times will not change the result after the resource is deleted.

## HTTP Status Codes in Detail
* 200 OK
  Request was successful and data is returned.
* 201 Created
  A new resource has been successfully created.
* 204 No Content
  Request was successful but no data is returned.
* 400 Bad Request
  Client has sent an invalid request.
* 401 Unauthorized
  Authentication is required.
* 403 Forbidden
  Client does not have permission.
* 404 Not Found
  Requested resource does not exist.
* 500 Internal Server Error
  Server encountered an error.

### REST API Workflow
* The client sends an HTTP request to the server.
* The request includes method, URI, headers, and sometimes a body.
* The server processes the request.
* The server sends back a response with status code and data.
* The client interprets the response and updates the UI.

## Advantages of REST
* High scalability due to stateless nature
* Flexibility in data formats
* Easy to understand and implement
* Better performance with caching
* Platform independent

## Limitations of REST
* Stateless nature increases client responsibility
* No strict contract like SOAP
* Handling transactions across multiple requests can be complex
* Overfetching or underfetching of data can occur

#### Conclusion
REST architecture is a powerful and flexible approach for building web services.
It is based on simple principles such as stateless communication, standard HTTP methods,
and resource-based interactions. Its simplicity, scalability, 
and compatibility with multiple platforms make it the most widely used architectural style in modern web development.

## References
* https://restfulapi.net/
* https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview
* https://www.geeksforgeeks.org/rest-api-introduction/
* https://www.javatpoint.com/restful-web-services-tutorial
