### What does REST mean?

**REST** (Representational State Transfer) - a set of rules (interface) that defines how two applications will communicate with each other using requests and responses.

**Requirements for REST:**

1. Client-server model.
2. Stateless operations (the server should not store information about the state). For example, when I send a request to */my-list*, the server should not know whether the client is logged in or whether they can access the information for this request. The server should receive an authentication token with the request to determine whether the user is currently logged in or not.
3. Logical interface. For example, to get a list of users, it is enough to make a *GET* request to */users*, and to get information about a user with *ID 345*, it is enough to make a *GET* request to */users/345*.

>The primary abstract concept in REST is a resource, understood as tables in a database. For example, for a REST API for an online toy store, the main resources would be toys, stores, and users.