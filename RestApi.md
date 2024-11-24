# 3. REST API (Representational State Transfer Application Programming Interface)

## What is a REST API?

- **Definition**: A REST API is a set of rules and conventions for building and interacting with web services using the **REST architectural style**.
- **Key Features**:
  - Stateless communication between client and server.
  - Resource representation (e.g., JSON or XML) for data exchange.
  - Use of HTTP methods (GET, POST, PUT, DELETE) to perform operations on resources.
- **Format**: Often uses **JSON** or **XML** for structured data exchange.
- **Endpoints**: URL paths that map to specific resources (e.g., `/users`, `/orders`).

---

## Why is a REST API Important?

1. **Scalability**:
   - REST APIs are stateless, making them easy to scale horizontally.
2. **Flexibility**:
   - Allows clients to interact with servers across different platforms.
3. **Interoperability**:
   - Enables integration between systems written in different languages.
4. **Standardization**:
   - Leverages standard HTTP methods and status codes for communication.
5. **Ease of Use**:
   - Simplifies communication for both developers and systems by using HTTP.

---

## Where Does a REST API Operate?

- **Client-Server Architecture**:
  - **Client**: Mobile apps, web browsers, or other services that consume the API.
  - **Server**: A backend service exposing REST endpoints.
- **Common Applications**:
  - Web apps, mobile apps, IoT devices, and third-party integrations.
- **Industries**:
  - E-commerce, social media, fintech, healthcare, and more.

---

## When is a REST API Used?

- **Building Web Services**:
  - Used for creating APIs for apps and services.
- **Integration Between Systems**:
  - For example, integrating payment gateways like Stripe or PayPal.
- **Data Sharing**:
  - Exposing or consuming APIs for data exchange.
- **Microservices Architecture**:
  - Enabling communication between microservices.

---

## How Does a REST API Work?

### Key Concepts:

1. **Resources**:
   - Data entities (e.g., `users`, `products`) are exposed via URLs.
   - Example: `/users` represents all users, `/users/1` represents a specific user.

2. **HTTP Methods**:
   - **GET**: Retrieve a resource.
   - **POST**: Create a resource.
   - **PUT**: Update a resource.
   - **DELETE**: Remove a resource.

3. **Stateless Communication**:
   - Each request is independent; no client data is stored on the server.

4. **HTTP Status Codes**:
   - **200 OK**: Request succeeded.
   - **201 Created**: Resource created.
   - **404 Not Found**: Resource not found.
   - **500 Internal Server Error**: Server error.

5. **Request and Response**:
   - **Request**: Contains method, headers, URL, and optional body.
   - **Response**: Contains status code, headers, and body.

---

## Scenario: Using a REST API in a Web Application

### Example: Fetching User Data

You want to fetch a list of users in a web application.

1. **Request**:
   - The frontend sends an HTTP `GET` request to the API endpoint `/users`.
   - Request Example:
     ```
     GET /users HTTP/1.1
     Host: api.example.com
     ```
2. **Processing**:
   - The server processes the request and retrieves the data from the database.
3. **Response**:
   - The server responds with the list of users in JSON format.
   - Response Example:
     ```json
     {
       "users": [
         { "id": 1, "name": "Alice" },
         { "id": 2, "name": "Bob" }
       ]
     }
     ```

---

## Visualization: REST API Flow

```mermaid
sequenceDiagram
  participant Client
  participant API
  participant Database
  Client->>API: HTTP GET /users
  API->>Database: Query users
  Database-->>API: Respond with user data
  API-->>Client: HTTP 200 OK + JSON response
