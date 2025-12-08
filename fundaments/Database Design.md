# Database Design

## Definition
Database Design is the process of structuring a database to organize data efficiently, ensure data integrity, optimize performance, and support application requirements through proper schema design, indexing, and normalization.

## Why Database Design is Essential
- **Ensures Data Integrity**: Maintains accuracy and consistency of data
- **Optimizes Performance**: Improves query speed and reduces latency
- **Facilitates Scalability**: Supports growth in data volume and user load
- **Enhances Maintainability**: Makes database easier to modify and extend
- **Reduces Redundancy**: Minimizes duplicate data through normalization

## Database Types

### SQL (Relational Databases)
**Characteristics**: Structured schema, ACID compliance, table relationships
**Examples**: MySQL, PostgreSQL, Oracle, SQL Server
**Best for**: Complex queries, transactional systems, data integrity

### NoSQL (Non-Relational Databases)
**Characteristics**: Flexible schema, horizontal scaling, various data models
**Examples**: MongoDB, Cassandra, Redis, DynamoDB
**Best for**: Large-scale, flexible data, high throughput

## Database Indexing

### 1. Primary Index
**Purpose**: Uniquely identifies each record
**Implementation**: Automatically created on primary key

### 2. Secondary Index
**Purpose**: Improves query performance on non-primary columns
**Implementation**: Manually created on frequently queried columns

### 3. Composite Index
**Purpose**: Index on multiple columns
**Implementation**: Created on columns often used together in queries

### 4. Unique Index
**Purpose**: Ensures column values are unique
**Implementation**: Prevents duplicate values in indexed column

## Normalization Forms

### 1NF (First Normal Form)
**Rule**: Eliminate duplicate columns, ensure atomic values
**Example**: Split address into street, city, state, zip

### 2NF (Second Normal Form)
**Rule**: Remove partial dependencies
**Example**: Move attributes dependent on part of primary key

### 3NF (Third Normal Form)
**Rule**: Remove transitive dependencies
**Example**: Move non-key attributes dependent on other non-key attributes

## Denormalization
**Purpose**: Improve read performance by adding redundancy
**Trade-off**: Faster reads vs data inconsistency risk
**Use when**: Read-heavy applications, reporting systems

## Partitioning Strategies

### 1. Horizontal Partitioning (Sharding)
**Method**: Split rows across multiple servers
**Benefit**: Distributes load, improves scalability
**Challenge**: Complex querying across shards

### 2. Vertical Partitioning
**Method**: Split columns across different tables
**Benefit**: Separates frequently vs rarely accessed data
**Challenge**: More joins required

### 3. Range Partitioning
**Method**: Partition based on value ranges
**Example**: Orders by date ranges (2023, 2024, 2025)

### 4. Hash Partitioning
**Method**: Partition using hash function
**Example**: Distribute users by hashed user_id

## CAP Theorem Application

### CP Systems (Consistency + Partition Tolerance)
**Databases**: MongoDB, Redis, HBase
**Use when**: Data consistency is critical

### AP Systems (Availability + Partition Tolerance)
**Databases**: Cassandra, DynamoDB, CouchDB
**Use when**: High availability is priority

### CA Systems (Consistency + Availability)
**Traditional**: Single-node databases (MySQL, PostgreSQL)
**Limitation**: Cannot handle network partitions

## Best Practices

### 1. Schema Design
- Use appropriate data types
- Define proper constraints (NOT NULL, UNIQUE)
- Establish foreign key relationships
- Plan for future growth

### 2. Indexing Strategy
- Index frequently queried columns
- Avoid over-indexing (impacts write performance)
- Use composite indexes for multi-column queries
- Regularly analyze and optimize indexes

### 3. Performance Optimization
- Normalize for write-heavy operations
- Denormalize for read-heavy operations
- Use connection pooling
- Implement query caching

### 4. Scalability Planning
- Plan for horizontal scaling from start
- Consider read replicas for heavy read loads
- Implement proper partitioning strategy
- Monitor and adjust as data grows
