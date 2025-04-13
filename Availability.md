### What is Availability?

Availability refers to the ability of a system to respond to user requests at any time. In distributed systems, it means the system continues to operate and provide responses even during partial failures or network issues. In CAP terms, a system is **available** if every request receives a (non-error) response.

---

### Measuring Availability

### 1. Uptime Percentage

|Availability Level|Downtime per Year|Downtime per Month|Downtime per Day|
|---|---|---|---|
|99%|3.65 days|7.30 hours|14.4 minutes|
|99.9% (Three 9s)|8.76 hours|43.2 minutes|1.44 minutes|
|99.99% (Four 9s)|52.6 minutes|4.32 minutes|8.6 seconds|
|99.999% (Five 9s)|5.26 minutes|25.9 seconds|0.86 seconds|

### 2. Formula

```
Availability = (Uptime) / (Uptime + Downtime)

```

### 3. Monitoring Tools

- Prometheus + Grafana
- AWS CloudWatch
- Datadog
- New Relic

---

### Key Components for High Availability

|Component|Purpose|Example Tool/Service|
|---|---|---|
|Load Balancer|Distribute traffic across instances|AWS ELB, NGINX, HAProxy|
|Auto-scaling|Add/remove instances dynamically|AWS Auto Scaling, GCP MIG|
|Redundant Instances|Ensure failover capability|Multi-AZ deployments|
|Database Replication|Avoid single point of failure in storage|MySQL Master-Slave, Aurora|
|Health Checks|Detect and remove failing components|Kubernetes Probes|
|Retry Mechanisms|Handle transient failures gracefully|Exponential Backoff|

---

### Examples of High Availability Systems

### 1. **Amazon DynamoDB**

- **Type:** AP system (under CAP)
- **Goal:** High availability with eventual consistency
- **Key Components:**
    - Partitioned, replicated storage
    - Quorum-based read/write
    - Automatic failover and scaling

### 2. **Netflix**

- **Goal:** Ensure continuous streaming and no downtime
- **Key Components:**
    - Edge servers via CDNs
    - Microservices and distributed architecture
    - Circuit breakers using Hystrix
    - Chaos Engineering tools (e.g., Chaos Monkey)

### 3. **Amazon S3**

- **Guarantee:** 99.99% availability
- **Key Components:**
    - Redundant storage across availability zones
    - Strong eventual consistency
    - Versioning and object replication

---

### Visual: Availability vs Consistency (Conceptual Graph)

```
Y-axis: Availability
X-axis: Consistency

   High
     |
     |\\
     | \\
     |  \\
     |   \\   <- AP systems (e.g., DynamoDB, Cassandra)
     |    \\
     |     \\   <- Balanced (e.g., Amazon S3)
     |      \\
     |       \\  <- CP systems (e.g., MongoDB with strict writes)
     |
     +---------------------------->
         Low           High

           Consistency

```

---

### Checklist for Designing for Availability

- [ ] Define SLA (e.g., 99.99% uptime)
- [ ] Use multi-zone/multi-region deployments
- [ ] Implement monitoring and alerting
- [ ] Include retry logic and exponential backoff
- [ ] Use load balancing across services
- [ ] Set up automatic failover and redundancy
- [ ] Gracefully handle degraded modes
- [ ] Test fault tolerance (e.g., Chaos Engineering)

---
