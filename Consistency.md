### What is Consistency?

Consistency ensures that **all nodes in a distributed system see the same data at the same time**. If a write operation is successful, all subsequent reads should return the updated value. It's one of the three pillars of the **CAP Theorem** and is often traded off for availability in real-world distributed systems.

In strict terms, consistency means behaving like a single, up-to-date copy of the data exists—regardless of how many servers or replicas the system uses.

---

### Types of Consistency Models

| Consistency Model    | Description                                                          | Example Use Case                |
| -------------------- | -------------------------------------------------------------------- | ------------------------------- |
| Strong Consistency   | Every read reflects the most recent write                            | Banking, payments               |
| Eventual Consistency | Reads may return stale data, but will eventually become consistent   | Social feeds, shopping carts    |
| Causal Consistency   | Writes that are causally related are seen by all nodes in order      | Collaborative docs, messaging   |
| Read-after-write     | Guarantees that a read after a user’s write will return updated data | User profile updates            |
| Monotonic Reads      | Once you read a value, you won't see an older value in future reads  | Session-based systems           |
| Session Consistency  | Guarantees consistency within a single session                       | Mobile apps, streaming sessions |

---

### How to Choose the Right Consistency

1. **Assess Business Needs:**
    - Can the system tolerate stale reads?
    - Is it okay to show different data to different users temporarily?
2. **Understand Read/Write Patterns:**
    - Systems with frequent writes may favor **eventual consistency** to maintain performance.
    - Read-heavy systems with critical data may require **strong consistency**.
3. **Latency vs Accuracy:**
    - Strong consistency may introduce latency due to synchronization.
    - Eventual consistency improves performance and availability but allows stale reads.

---

### Examples of Consistency in Real Systems

|System|Consistency Level|Notes|
|---|---|---|
|**MongoDB**|Tunable|Can configure read/write concern for stronger or looser consistency|
|**Cassandra**|Eventual|Uses quorum-based reads/writes for tunable consistency|
|**Amazon DynamoDB**|Eventual by default|Can opt-in for strongly consistent reads|
|**Spanner (Google)**|Strong|Uses TrueTime API to guarantee external consistency|
|**Redis**|Strong (single node), eventual (cluster)|Data loss can happen without persistence|

---

### Graph: Consistency vs Latency (Conceptual)

```
Y-axis: Latency
X-axis: Consistency

   High
     |
     |       * <- Strong Consistency (Spanner, HBase)
     |
     |    *
     |       <- Read-after-write, Monotonic
     |
     |  *
     |       <- Eventual (Cassandra, DynamoDB default)
     |
     +---------------------------->
         Low         High

           Consistency

```

---

### Pros and Cons of Strong vs Eventual Consistency

|Property|Strong Consistency|Eventual Consistency|
|---|---|---|
|Data Freshness|Always up-to-date|May be stale temporarily|
|Availability|Lower during network partitions|High|
|Performance|Higher latency|Lower latency|
|Complexity|Simpler to reason about|Requires conflict resolution|
|Use Case Suitability|Critical data|User-generated or social data|

---

### Design Considerations for Consistency

- [ ] Do users expect to see real-time updates?
- [ ] Will inconsistency lead to data loss or incorrect behavior?
- [ ] Is it okay to show eventually correct results?
- [ ] Can the system handle data conflicts and merge strategies?

---

## Key Components & Practices to Achieve Consistency

Achieving consistency in a distributed system requires careful architectural and operational choices. Below are the main building blocks and strategies used to ensure different levels of consistency.

---

### Core Components for Consistency

|Component|Purpose|Examples|
|---|---|---|
|**Quorum Protocols**|Ensure a majority of nodes agree before committing a read/write|Cassandra, DynamoDB|
|**Leader Election**|One node acts as the authoritative source of truth|Raft, Paxos, Zookeeper|
|**Replication Strategies**|Synchronously replicate data to ensure consistency|MongoDB (primary-secondary), Spanner|
|**Consensus Algorithms**|Ensure all nodes agree on the order of updates|Raft, Paxos, Zab|
|**Write-Ahead Logs (WAL)**|Maintain a log of changes to ensure consistency after failures|PostgreSQL, MySQL, etc.|
|**Vector Clocks / Timestamps**|Track causal relationships between updates|Dynamo, Riak|
|**Versioning / Conflict Resolution**|Detect and resolve write conflicts|CRDTs, LWW (last write wins)|

---

### Design Practices to Maintain Consistency

|Practice|Description|
|---|---|
|**Synchronous Writes**|Wait for data to be written to all replicas before acknowledging success|
|**Read/Write Quorums**|Require a minimum number of nodes to confirm a read/write operation|
|**Data Partitioning with Strong Leaders**|Ensure a leader per shard manages writes|
|**Consistency Levels (Tunable)**|Allow clients to choose between strong and eventual per request|
|**Retry with Idempotency**|Ensure retrying a failed operation doesn't create duplicate writes|
|**Read Repair / Anti-Entropy**|Compare and fix inconsistent replicas in the background|
|**Time Synchronization**|Use NTP or specialized services to maintain consistent ordering (e.g., TrueTime)|
|**Client Session Management**|Maintain state for users to ensure monotonic reads or session guarantees|

---

### Example Strategy: Quorum-based Consistency

To achieve **tunable consistency** using quorum logic:

```
W + R > N

```

- `W`: number of nodes required for a write to succeed
- `R`: number of nodes required for a read
- `N`: total number of replicas

This ensures that read and write sets always intersect, allowing at least one node to have the most recent value.

---

### Testing Consistency in Practice

- Simulate network partitions and node failures
- Use **Jepsen** testing for consistency anomalies

Jepsen is a software testing framework used to evaluate distributed systems by simulating network partitions and checking for consistency violations and other anomalies that might occur during system failures.

- Implement **chaos engineering** for consistency under real failure conditions

Chaos engineering is a practice of deliberately introducing controlled failures and disruptions into a system to test its resilience and verify that it maintains consistency and reliability under adverse conditions.

---

### Summary Checklist

- [ ] Use strong leaders for write consistency
- [ ] Tune quorum values for R/W balance
- [ ] Implement WALs and replication
- [ ] Use conflict resolution and versioning
- [ ] Monitor replication lag and consistency metrics
- [ ] Provide client-facing consistency guarantees (e.g., read-after-write)

---
