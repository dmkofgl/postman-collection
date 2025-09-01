# postman-collection

## Theory of REST API

At the most basic level, an API is a mechanism that enables an application or service to access a resource within another application,
service.
REST (Representational State Transfer) is a set of architectural constraints, not a protocol or a standard. API developers can implement
REST in a variety of ways.

- A `client-server architecture` made up of clients, servers, and resources, with requests managed through HTTP.
- `Stateless` client-server communication, meaning no client information is stored between get requests and each request is separate and
  unconnected.
- `Cacheable` data that streamlines client-server interactions.
- `A uniform interface` between components so that information is transferred in a standard form. This requires that:
    - resources `requested are identifiable and separate from the representations `sent to the client.
    - resources `can be manipulated by the client via the representation` they receive because the representation contains enough information
      to do so.
    - self-descriptive `messages returned to the client have enough information to describe how the client should process it`. E.g MIME-type
    - `hypertext/hypermedia is available`, meaning that after accessing a resource the client should be able to use hyperlinks to find all
      other currently available actions they can take.
- A `layered` system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval
  of requested information into hierarchies, invisible to the client.
- `Code-on-demand (optional)`: the ability to send executable code from the server to the client when requested, extending client
  functionality.

## Basic Postman functions (collections, requests, variables).

### Collections
A **collection** is a way to organize your requests.

**Benefits of collections:**
- Group related requests together.
- Share APIs with your team.
- Run multiple requests in sequence using the **Collection Runner**.

**Steps to create a collection:**
1. Click **New → Collection**.
2. Give it a name.
3. Save requests inside the collection.
4. Organize requests in folders for better structure.
5. 
###  Requests
A **request** is how Postman interacts with an API.

**Components of a request:**
- **Method:** HTTP methods like `GET`, `POST`, `PUT`, `DELETE`, etc.
- **URL/Endpoint:** The API address you want to call.
- **Headers:** Extra information sent with the request (e.g., `Authorization`, `Content-Type`).
- **Body:** Data sent with the request (used in `POST`, `PUT`, `PATCH`).
- **Params:** Query parameters appended to the URL (e.g., `?id=123&name=John`).

**Steps to create a request:**
1. Click **+ New Request**.
2. Enter the URL.
3. Select the HTTP method.
4. Add headers, params, or body if needed.
5. Click **Send** to execute the request and see the response.

### Variables
**Variables** are placeholders that make requests dynamic and reusable.

**Types of variables:**
- **Global Variables:** Accessible across all collections and requests.
- **Collection Variables:** Only available in a specific collection.
- **Environment Variables:** Different sets of variables for different environments (e.g., Dev, QA, Prod).
- **Local Variables:** Specific to a single request or script.

**Example:**
Instead of hardcoding the URL:
https://api.example.com/users/123

Use variables:
{{base_url}}/users/{{user_id}}

Define:
- `base_url = https://api.example.com`
- `user_id = 123`

**Steps to use variables:**
1. Go to **Environments → Add Environment**.
2. Create key-value pairs.
3. Use `{{variable_name}}` in requests.
4. Switch environments as needed.
