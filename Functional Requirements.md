### 1. **Understand the Business Goals**

- **What is the purpose of the system?**
    
    (E.g., Enable online shopping, manage data analytics, automate customer support)
    
- **Who are the stakeholders?**
    
    (E.g., Users, product owners, admins, external systems)
    
- **What are the main business processes?**
    
    (E.g., User registration, product search, transaction processing)
    

---

### 2. **Identify the Primary System Functions**

- **Core features:**
    
    What are the core features your system must provide?
    
    (E.g., authentication, search functionality, checkout process)
    
- **User Actions:**
    
    What actions will users take in the system?
    
    (E.g., User logins, data submission, file uploads)
    
- **System Responses:**
    
    How does the system respond to these actions?
    
    (E.g., display results, send notifications, update database)
    
- **Data Inputs and Outputs:**
    
    What inputs will the system accept, and what outputs will it produce?
    
    (E.g., data from a user form, email notifications)
    

---

### 3. **User Roles and Permissions**

- **What are the different user roles?**
    
    (E.g., Admin, registered user, guest)
    
- **What actions are allowed for each role?**
    
    (E.g., Admin can add/edit/delete content, users can view and interact)
    
- **Are there any restrictions on certain actions?**
    
    (E.g., Admin has access to all records, users can only see their data)
    

---

### 4. **Data Management Requirements**

- **What type of data will be handled?**
    
    (E.g., User profile data, transactional data, inventory data)
    
- **How is data created, updated, and deleted?**
    
    (E.g., User can update their profile, admins can delete records)
    
- **What data validations are needed?**
    
    (E.g., email format, date of birth, inventory quantity)
    
- **What are the data storage and retrieval requirements?**
    
    (E.g., Querying data, generating reports, exporting data)
    
- **What data privacy and security considerations exist?**
    
    (E.g., Personal information must be encrypted)
    

---

### 5. **Performance Requirements**

- **What is the expected load on the system?**
    
    (E.g., 10,000 users concurrently accessing the system)
    
- **What are the response time requirements?**
    
    (E.g., The system should respond within 3 seconds for most user actions)
    
- **What are the uptime and availability expectations?**
    
    (E.g., 99.9% availability, minimal downtime during maintenance)
    

---

### 6. **System Interaction**

- **Does the system interact with other systems?**
    
    (E.g., third-party payment gateways, external databases, APIs)
    
- **What [[API]] or integration points are needed?**
    
    (E.g., REST APIs for user authentication, payment processing)
    
- **What protocols are used for system communication?**
    
    (E.g., HTTP, WebSocket, MQTT)
    

---

### 7. **Error Handling and Logging**

- **What happens if the system encounters an error?**
    
    (E.g., User sees an error message, system retries the request)
    
- **How should errors be logged?**
    
    (E.g., Log critical errors in a centralized system, alert admins)
    
- **What user feedback is provided on errors?**
    
    (E.g., Provide clear error messages, offer recovery steps)
    

---

### 8. **Scalability and Growth**

- **What is the expected growth of users/data over time?**
    
    (E.g., Expected to support 100,000 users in 3 years)
    
- **How should the system scale as load increases?**
    
    (E.g., Add new nodes, use load balancing, partitioning)
    
- **How is the system expected to handle increased traffic?**
    
    (E.g., Auto-scaling based on demand, server clustering)
    

---

### 9. **Security and Compliance Requirements**

- **What are the security requirements?**
    
    (E.g., HTTPS, multi-factor authentication, role-based access control)
    
- **Are there any regulatory or compliance requirements?**
    
    (E.g., GDPR, HIPAA, PCI-DSS)
    
- **What data protection measures are required?**
    
    (E.g., Data encryption, data anonymization)
    

---

### 10. **Documentation and Reporting**

- **What reporting functionality is needed?**
    
    (E.g., Generate sales reports, view user activity logs)
    
- **What formats should reports be available in?**
    
    (E.g., CSV, PDF, Excel)
    
- **Who will have access to the reports?**
    
    (E.g., Admins, managers)
    

---

### 11. **User Experience and Interface**

- **What is the expected user experience?**
    
    (E.g., Easy navigation, clear feedback on user actions)
    
- **What interface requirements exist?**
    
    (E.g., Web UI, mobile-responsive design, accessibility features)
    
- **Are there any user interaction requirements?**
    
    (E.g., Easy login, search suggestions, filtering)
    

---

### Sample Functional Requirements Template

Here’s a simple template to organize your functional requirements:

---

**Functional Requirement ID:** FR-001

**Description:** The system shall allow users to create an account using an email and password.

**Priority:** High

**Actors:** End user

**Input:** Email address, password

**Output:** User account created, confirmation email sent

**Validation:** Email format validation, password strength validation

**Assumptions:** User has internet access

**Dependencies:** Email service integration

---

### Quick Tips for Identifying Functional Requirements

- **Talk to stakeholders:** Always engage with the end users, business analysts, product managers, and developers to gather their needs.
- **Break it down by user journey:** Identify the key actions users will take, and document what the system must do for each action.
- **Focus on the system’s behavior:** Think about the actions, responses, and interactions needed for the system to operate properly.
- **Use use cases and user stories:** These help in breaking down high-level requirements into smaller, more actionable tasks.

---

This cheat sheet will help you capture functional requirements efficiently, ensuring your system design aligns with both user needs and business goals. Let me know if you’d like further breakdowns of specific examples or need templates for non-functional requirements as well!