### 1. **Performance**

- **Response Time**: How fast should the system respond to user interactions or API requests?
    - Example: The system should respond to a user request in less than 3 seconds.
- **Throughput**: How many requests, transactions, or operations should the system handle per unit of time?
    - Example: The system should support 100,000 transactions per minute.
- **Latency**: What is the maximum acceptable delay for a system operation (e.g., query execution)?
    - Example: Database queries should execute within 100ms.
- **Concurrency**: How many users or processes should the system be able to handle concurrently?
    - Example: The system should support 10,000 concurrent users.

---

### 2. **Availability**

- **Uptime**: What is the expected [[availability]] of the system?
    - Example: The system should have 99.9% uptime (less than 8 hours of downtime per year).
- **Failover and Redundancy**: How should the system behave in the event of component failures?
    - Example: The system should automatically failover to a backup server within 30 seconds of a failure.
- **Disaster Recovery**: What processes should be in place for recovering the system from failures?
    - Example: The system should be able to restore data from backups within 24 hours after a disaster.

---

### 3. **Scalability**

- **Horizontal Scalability**: Can the system be expanded by adding more nodes or resources to handle increased load?
    - Example: The system should scale horizontally by adding more web servers as traffic increases.
- **Vertical Scalability**: Can the system be upgraded by adding more resources (e.g., CPU, RAM) to handle greater demand?
    - Example: The system should scale vertically to use up to 16 cores and 64GB of RAM for processing.
- **Elasticity**: Can the system automatically adjust resources (e.g., scaling up/down) in response to demand?
    - Example: The system should automatically scale up during peak hours and scale down during off-peak times.

---

### 4. **Security**

- **Authentication**: How should users or systems authenticate to the system?
    - Example: Users must authenticate using multi-factor authentication (MFA).
- **Authorization**: What levels of access or roles are needed, and how should they be enforced?
    - Example: Admins should have full access, while users can only access their own data.
- **Data Encryption**: What encryption methods should be used to protect sensitive data?
    - Example: All sensitive data must be encrypted at rest and in transit using AES-256 encryption.
- **Auditing and Logging**: What events should be logged, and who can access the logs?
    - Example: All login attempts should be logged, and logs should be accessible only to security personnel.
- **Compliance**: What industry standards or regulations must the system adhere to?
    - Example: The system must comply with GDPR and PCI-DSS for handling personal and payment information.

---

### 5. **Maintainability**

- **Code Quality and Documentation**: How will the system be structured and documented to allow easy maintenance?
    - Example: The system must follow coding standards and have complete documentation for each API and module.
- **Error Reporting**: How should the system handle and report errors?
    - Example: Errors should be automatically logged, and an alert should be sent to the admin team for critical issues.
- **Modularity**: How easily can individual components of the system be modified or replaced?
    - Example: The system should use microservices to allow independent updates to services without affecting the entire system.

---

### 6. **Usability**

- **User Interface**: What user interface requirements are necessary for ease of use?
    - Example: The system should have an intuitive user interface with a mobile-responsive design.
- **Accessibility**: What accessibility standards must the system comply with?
    - Example: The system should comply with WCAG 2.1 Level AA for accessibility.
- **Training and Support**: What is the level of training or support required for users?
    - Example: A help center should be available, and users should receive an onboarding tutorial.

---

### 7. **Interoperability**

- **System Integration**: How will the system interact with other systems or third-party services?
    - Example: The system should support integration with external payment gateways via REST APIs.
- **Standards Compliance**: Does the system need to comply with any industry standards for data exchange or protocols?
    - Example: The system must support HL7 for healthcare data exchange.
- **Data Formats**: What data formats should be supported for input/output or communication?
    - Example: The system should accept and return data in JSON format.

---

### 8. **Reliability**

- **Fault Tolerance**: How resilient is the system to failures and how does it recover?
    - Example: The system should recover within 1 minute if a node goes down.
- **Error Recovery**: What should happen if the system encounters an error or failure?
    - Example: The system should have retry mechanisms for transient failures.
- **Data Integrity**: How is the integrity of data preserved during failures?
    - Example: The system should use transactional consistency to ensure that partial data updates are not committed.

---

### 9. **Legal and Compliance Requirements**

- **Data Retention**: What data should be stored, and for how long?
    - Example: The system must retain user transaction data for 5 years for compliance.
- **Regulatory Compliance**: What local or global laws govern data handling and storage?
    - Example: The system must comply with GDPR, CCPA, and other data protection laws.

---

### 10. **Environmental Requirements**

- **Hardware/Software Constraints**: What hardware or software limitations are present?
    - Example: The system should be able to run on Linux-based servers and support PostgreSQL 12.x.
- **System Resource Constraints**: What are the CPU, memory, or disk space requirements?
    - Example: The system should be able to run on a machine with at least 8GB of RAM and 500GB of SSD storage.

---

### Summary Template for Non-Functional Requirements

**Non-Functional Requirement ID:** NFR-001

**Description:** The system must be capable of handling 10,000 concurrent users without degrading performance.

**Priority:** High

**Acceptance Criteria:**

- Response time must not exceed 3 seconds per user request during peak traffic.
- The system must scale horizontally by adding more servers as user load increases.

---

### Quick Tips for Identifying Non-Functional Requirements

- **Collaborate with stakeholders**: Discuss non-functional expectations such as system performance, security, and user experience with relevant stakeholders.
- **Define clear metrics**: Quantify the requirements wherever possible (e.g., response time, uptime, etc.).
- **Use industry benchmarks**: Refer to industry standards for performance, security, and compliance.
- **Testable criteria**: Ensure that non-functional requirements are measurable (e.g., “99.9% uptime” is testable, but “high performance” is not).

---

[CAP Theorem](https://www.notion.so/CAP-Theorem-1ccdf0bc7b5a80689659dd6df699a5a9?pvs=21)

[Determining number of users](https://www.notion.so/Determining-number-of-users-1ccdf0bc7b5a8032b517e7513ccd0fb5?pvs=21)

[Selecting the databse](https://www.notion.so/Selecting-the-databse-1ccdf0bc7b5a809ea315f787d1c3c62c?pvs=21)

[Scalability](https://www.notion.so/Scalability-1ccdf0bc7b5a807a8c01eb91b9948859?pvs=21)