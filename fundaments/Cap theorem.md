# CAP Theorem

## Definition
CAP Theorem, also known as Brewer's Theorem, states that in a distributed computer system, you can only guarantee two out of three properties simultaneously: Consistency, Availability, and Partition Tolerance.

## The Three Properties

### Consistency
**Definition**: Every read receives the most recent write or an error
**What it means**: All nodes see the same data at the same time
**Example**: Banking systems where balance must be accurate

### Availability
**Definition**: Every request receives a response (non-error)
**What it means**: System continues operating during failures
**Example**: Social media platforms that prioritize uptime

### Partition Tolerance
**Definition**: System continues operating despite network failures
**What it means**: Works despite network splits between nodes
**Example**: Distributed databases across multiple data centers

## CAP Trade-offs

### CA Systems (Consistency + Availability)
**Characteristics**: Works when no network partitions occur
**Examples**: Traditional single-node databases (MySQL, PostgreSQL)
**Limitation**: Cannot handle network partitions

### CP Systems (Consistency + Partition Tolerance)
**Characteristics**: Maintains consistency during network partitions
**Examples**: MongoDB, Redis, HBase
**Behavior**: Returns errors during partitions to maintain consistency

### AP Systems (Availability + Partition Tolerance)
**Characteristics**: Maintains availability during network partitions
**Examples**: Cassandra, DynamoDB, CouchDB
**Behavior**: Returns potentially stale data but remains available

## Real-World Applications

### Banking Systems (CP)
**Priority**: Consistency over availability
**Reason**: Cannot have inconsistent account balances
**During partition**: Returns error rather than wrong balance

### Social Media (AP)
**Priority**: Availability over consistency
**Reason**: Better to show slightly old data than be unavailable
**During partition**: Shows cached/stale data but remains accessible

### E-commerce (CP/AP based on feature)
**Product catalog (AP)**: Shows available products with eventual consistency
**Shopping cart (CP)**: Ensures cart consistency across sessions
**Order processing (CP)**: Guarantees order consistency and accuracy

## BASE vs ACID

### ACID (Traditional Databases)
**Atomicity**: All or nothing transactions
**Consistency**: Database rules are always followed
**Isolation**: Transactions don't interfere
**Durability**: Committed transactions persist
**Used in**: CP systems, financial applications

### BASE (NoSQL Databases)
**Basically Available**: System seems to work all the time
**Soft state**: State may change without input
**Eventual consistency**: Becomes consistent over time
**Used in**: AP systems, high-scale applications

## Practical Implications

### When to Choose CP
- Financial transactions
- Inventory management
- Voting systems
- Any system where data accuracy is critical

### When to Choose AP
- Social media feeds
- Product recommendations
- Comment systems
- Systems where uptime is more important than perfect data

### Network Partitions in Practice
**Frequency**: More common than expected in distributed systems
**Causes**: Network failures, data center issues, maintenance
**Impact**: Forces CAP choice to become relevant

## Common Misconceptions

### 1. "You Must Choose Only Two"
**Reality**: Systems can be tuned for different scenarios
**Example**: Some databases offer tunable consistency levels

### 2. "CAP Only Applies to Distributed Systems"
**Reality**: Single-node systems are CA by default
**Note**: They become distributed when scaled/replicated

### 3. "Partitions are Rare"
**Reality**: Network issues are common in cloud environments
**Impact**: CAP becomes relevant in production systems

## Modern Approaches

### Tunable Consistency
**Concept**: Adjust consistency level per operation
**Examples**: Cassandra's consistency levels (ONE, QUORUM, ALL)
**Use case**: Balance between consistency and performance

### Hybrid Systems
**Approach**: Use CP for critical data, AP for non-critical
**Example**: Banking app: CP for balance, AP for transaction history

### Consensus Algorithms
**Solution**: Achieve consistency during partitions
**Examples**: Paxos, Raft
**Used in**: etcd, ZooKeeper, distributed ledgers

## Key Takeaways

### 1. Understand Your Requirements
- What data must be perfectly consistent?
- What can be eventually consistent?
- How important is uptime vs accuracy?

### 2. Design for Your Use Case
- Financial systems → CP
- Social applications → AP
- Hybrid approaches for mixed requirements

### 3. Monitor and Adjust
- Track partition occurrences
- Measure consistency/availability trade-offs
- Adjust configurations as needed

### 4. Remember the "P" is Mandatory
In distributed systems, partition tolerance cannot be sacrificed
Choice is actually between C and A during partitions
