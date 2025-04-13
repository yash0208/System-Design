
1. **Understand the Problem Statement**
    - Clarify requirements ([[Functional Requirements]] & [[Non-Functional Requirements]])
    - Identify constraints (scale, latency, consistency, etc.)
    - Ask clarifying questions if needed
2. **Define Scope and Features**
    - Break the system into core features and optional features
    - Set clear boundaries for the problem
3. **Back-of-the-Envelope Estimation**
    - Estimate scale: users, QPS, storage, bandwidth
    - Helps guide your tech choices and design direction
4. **Define APIs**
    - Draft key APIs for the main components
    - Think in terms of clients and external systems
5. **High-Level Design**
    - Identify main components (e.g., frontend, backend, DB, cache, queue)
    - Show how they interact (basic architecture diagram)
6. **Component Deep Dive**
    - Dive into each major component
    - Justify design choices (e.g., SQL vs NoSQL, sync vs async)
7. **Data Modeling**
    - Design schema (relational or document-based)
    - Consider indexing, partitioning, replication
8. **Scalability & Reliability**
    - How to scale components (horizontal/vertical)
    - Use of load balancers, caching layers, CDNs
    - Fault tolerance strategies (replication, retries, backups)
9. **Caching Strategy**
    - What to cache, where to cache (DB results, API responses)
    - TTL, eviction policies
10. **Database Design**
    - Choose appropriate DB type
    - Consistency model (CAP theorem trade-offs)
    - Read/write patterns
11. **Async Processing**
    - Use of queues, workers, schedulers
    - For tasks like email sending, image processing, etc.
12. **Security & Privacy**
    - Authentication, authorization
    - Encryption (data at rest, in transit)
    - Rate limiting, input validation
13. **Monitoring & Alerting**
    - Log collection, health checks, metrics
    - Tools: Prometheus, Grafana, ELK stack, etc.
14. **Bottlenecks & Trade-offs**
    - Identify potential weak points
    - Explain design decisions and trade-offs
15. **Wrap-Up**
    - Summarize the design
    - Call out open questions or future improvements