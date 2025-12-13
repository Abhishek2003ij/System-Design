# **Caching**

## **Definition**
Caching is a technique that stores frequently accessed data in a temporary, high-speed storage layer to reduce access time, decrease load on the primary database, and improve system performance.

---

## **Why Caching is Essential**
- **Reduces Latency**: Faster access from memory vs disk/database.  
- **Decreases Load**: Minimizes calls to the primary data source  
- **Improves Scalability**: Handles more traffic with the same backend resources  
- **Enhances User Experience**: Faster response times  
- **Saves Cost**: Reduces database and infrastructure overhead  

---

## **Caching Illustration**
![Caching Diagram](https://github.com/user-attachments/assets/caching-diagram-url)

_Image credit: Technical documentation_

---

# **Caching Strategies (Data Management Techniques)**

## **1. Cache-Aside (Lazy Loading)**
- Application checks the cache first  
- If data is missing, it loads from the database and updates the cache  

**Best for:** Read-heavy workloads

---

## **2. Write-Through**
- Data is written to both cache and database simultaneously  

**Best for:** Strong consistency requirements

---

## **3. Write-Behind (Write-Back)**
- Data is first written to the cache  
- Database writes happen asynchronously in the background  

**Best for:** High write throughput systems

---

## **4. Read-Through**
- Cache sits between the app and database  
- Automatically loads missing data on cache miss  

**Best for:** Transparent caching layers

---

# **Cache Eviction Policies (Removal Techniques)**

## **1. Least Recently Used (LRU)**
- Removes items that haven't been accessed recently  
- **Implementation**: Track access timestamps  

---

## **2. First In First Out (FIFO)**
- Removes items in the order they were added  
- **Implementation**: Queue structure  

---

## **3. Least Frequently Used (LFU)**
- Removes items with the lowest access frequency  
- **Implementation**: Maintain usage counters  

---

## **4. Time To Live (TTL)**
- Automatically expires items after a fixed duration  
- **Implementation**: Store expiry timestamps  
