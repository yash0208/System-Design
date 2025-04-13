### What is the CAP Theorem?

The **CAP Theorem**, also known as **Brewer’s Theorem**, states that in a **distributed data system**, you can only **guarantee two out of the following three properties** at any given time:

- **[[Consistency]] (C):** Every read receives the most recent write or an error.
- **[[Availability]] (A):** Every request receives a (non-error) response, without guarantee that it contains the most recent write.
- **[[Partition Tolerance]] (P):** The system continues to operate despite network partitions or communication breakdowns between nodes.

### Why is CAP Important?

Distributed systems often need to deal with unreliable networks. The CAP theorem helps guide trade-offs in system design when network issues (partitions) are inevitable. It forces architects to decide whether to favor consistency or availability during those partitions.

### Real-World Interpretations

- **CP System (Consistency + Partition Tolerance):**
    - Prioritizes accuracy of data over availability
    - Example: HBase, MongoDB (when configured to be consistent)
    - Use Case: Banking systems, ledgers, where stale data is unacceptable
- **AP System (Availability + Partition Tolerance):**
    - Prioritizes uptime over strict consistency
    - Example: Couchbase, Cassandra, DynamoDB
    - Use Case: Messaging apps, real-time analytics, systems that can tolerate eventual consistency
- **CA System (Consistency + Availability):**
    - Only possible in the absence of network partitions
    - Typically applies to single-node systems or tightly coupled clusters

### How to Use CAP Theorem in Design

1. **Assess Business Requirements:**
    - Is stale data acceptable temporarily?
    - Is downtime acceptable under partition scenarios?
2. **Evaluate the Impact of Each Trade-off:**
    - In systems needing immediate data accuracy (e.g., financial transactions), consistency may be more critical than availability.
    - In user-facing systems (e.g., social media timelines), availability may be more valuable than strong consistency.
3. **Design Around Your Priorities:**
    - Choose databases and architecture patterns that align with your trade-offs.
    - For AP systems, implement eventual consistency mechanisms (conflict resolution, timestamps, vector clocks).
    - For CP systems, be prepared for system unavailability during partitions.

### What to Check When Applying CAP

- What is the acceptable consistency model: strong, eventual, or causal?
- How often do partitions happen in your deployment environment?
- Can the system afford to return stale or inconsistent data temporarily?
- What is the cost of unavailability versus serving stale data?

---
