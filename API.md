## 1. **What is the Role of APIs in System Design**

APIs are the **interfaces** that expose functionality of a service or component to others. In system design, they:

- Define **how services communicate** (internal and external).
    
- Help in **modularizing** the system.
    
- Enable **interoperability** between services (microservices, third-party integration).
    
- Impact **performance**, **security**, and **scalability** of the system.
    

---

## 2. **When Asked to Design a System — API Planning Approach**

### Step 1: Understand Functional Requirements

- What operations should the system support?
    
- Who will call the API (client, other services, admin panel, etc.)?
    

**Example**: If designing a URL shortening service, expected APIs might be:

- `POST /shorten` — create a short URL
    
- `GET /{shortCode}` — redirect to original URL
    
- `GET /stats/{shortCode}` — get analytics
    

### Step 2: Define Core Resources and Actions (RESTful Thinking)

- Identify **nouns** (resources) and **verbs** (actions).
    
- Choose between:
    
    - **REST API** (resource-oriented)
        
    - **GraphQL API** (flexible querying)
        
    - **gRPC** (high-performance, binary protocol, microservices)
        

Use REST for:

- Public APIs
    
- Simpler CRUD operations
    
- Broad client compatibility
    

Use GraphQL when:

- Clients need custom queries
    
- You want to reduce over-fetching or under-fetching
    

Use gRPC when:

- Internal microservice-to-microservice communication
    
- Low latency and high throughput are needed
    

---

## 3. **Designing API Contracts**

### Key decisions: [[Best Design Practices for REST APIs]]

- **HTTP Methods**: Use appropriately (`GET`, `POST`, `PUT`, `DELETE`)
    
- **Naming Conventions**: Keep URLs semantic and hierarchical
    
- **Request/Response Structure**: Define payloads (use versioning, handle errors, add metadata)
    
- **Authentication**: Who can access what (OAuth, API Keys, JWT, etc.)
    
- **Rate Limiting**: Prevent abuse and control traffic
    
- **Idempotency**: Especially for `PUT` and `DELETE`
    

**Example**: In a payment system

- `POST /payments` should be **idempotent** — retrying should not double charge
    
- Implement **retry tokens** or idempotency keys
    

---

## 4. **API Gateway and Management**

In larger systems:

- Place an **API Gateway** in front of services
    
- Handles:
    
    - Rate limiting
        
    - Authentication
        
    - Routing
        
    - Caching
        
    - Observability (metrics, logs)
        

---

## 5. **Non-Functional Considerations**

|Factor|What to Ask|
|---|---|
|**Latency**|How fast should the API respond?|
|**Availability**|Can this API tolerate downtime?|
|**Scalability**|Will this API handle high traffic?|
|**Security**|How is authentication and authorization enforced?|
|**Consistency**|Should operations be strongly or eventually consistent?|
|**Monitoring**|Are logs and metrics collected? Are alerts in place?|

---

## 6. **Documentation and Discoverability**

- APIs should be well-documented (Swagger/OpenAPI specs)
    
- Should include:
    
    - Parameters
        
    - Expected responses
        
    - Error codes
        
    - Rate limits
        

---

## 7. **Versioning Strategy**

APIs should be versioned from the beginning to avoid breaking changes.

- URL versioning: `/v1/users`
    
- Header versioning: `Accept: application/vnd.company.v1+json`
    

Choose based on client flexibility and long-term maintenance.

---

## 8. **Examples of API Design from Real Systems**

### Twitter

- `POST /tweets`: Publish a tweet
    
- `GET /users/{id}/timeline`: Fetch user tweets
    

### Instagram

- `POST /media`: Upload a photo
    
- `GET /feed`: Show timeline
    
- `POST /likes`: Like a post
    

These follow REST principles and return structured data (usually JSON).

---

## Summary: What to Consider When Designing APIs

|Consideration|Explanation|
|---|---|
|**Purpose of API**|What function it serves in the system|
|**Type of API**|REST, GraphQL, gRPC|
|**Endpoints**|Well-defined, versioned, RESTful routes|
|**Security**|Authentication, authorization, data protection|
|**Rate Limits**|Protect resources and prevent abuse|
|**Error Handling**|Clear, consistent, well-defined codes|
|**Monitoring**|Logs, metrics, tracing|
|**Documentation**|Developer-friendly API specs and usage|
|**Idempotency**|Especially for financial or critical operations|
|**Scalability & Availability**|Designed to handle high load and failures|

---
