# Load Balancing

## Definition
Load balancing involves distributing incoming web or network requests across multiple available servers to ensure no single server becomes overwhelmed, thereby improving responsiveness, availability, and reliability of applications.

## Why Load Balancing is Essential
- **Prevents Server Overload**: Distributes traffic evenly across servers
- **Increases Availability**: If one server fails, others continue handling requests
- **Improves Performance**: Reduces response time by distributing load
- **Enables Horizontal Scaling**: Allows adding more servers seamlessly
- **Provides Flexibility**: Enables maintenance without downtime

## Load Balancer Illustration
![Load Balancer Diagram](https://github.com/user-attachments/assets/ae9f41d6-f2ca-4ddf-bdff-5514bf554aa6)

Image credit: https://www.cloud4u.com/blog/what-is-a-load-balancer-and-its-types/

## Load Balancing Algorithms (Decision Techniques)

### 1. Round Robin
Distributes requests sequentially across servers in rotation.
Request 1 → Server A
Request 2 → Server B  
Request 3 → Server C
Request 4 → Server A (repeat)
**Best for**: Servers with identical specifications

### 2. Weighted Round Robin
Round Robin with capacity weighting - higher weight servers receive more requests.
Server A (Weight 3) → 3 requests
Server B (Weight 1) → 1 request
Server C (Weight 2) → 2 requests
**Best for**: Mixed hardware environments with varying server capacities

### 3. Least Connections
Sends request to server with fewest active connections.
Server A: 15 connections
Server B: 8 connections (New request goes here)
Server C: 22 connections
**Best for**: Applications with long-lived connections like WebSockets or database sessions

### 4. IP Hash
Uses client IP address to determine server assignment via hashing.
hash("192.168.1.10") → Server B (always)
hash("192.168.1.11") → Server A (always)
**Best for**: Session persistence requirements

### 5. Least Response Time
Selects server with fastest response time combined with fewest connections.
Server A: 50ms response, 10 connections
Server B: 30ms response, 15 connections
Server C: 20ms response, 5 connections (Selected)
**Best for**: Performance-critical applications where response time is crucial

## Types of Load Balancers

### Layer 4 Load Balancer (Transport Layer)
- Operates at TCP/UDP level
- Faster but less intelligent routing
- Example: Directs traffic based on IP addresses and ports

### Layer 7 Load Balancer (Application Layer)
- Operates at HTTP/HTTPS level
- Can make routing decisions based on content
- Example: Routes `/api` requests to API servers, `/static` to file servers

## Popular Load Balancing Solutions

### Software Load Balancers
- **NGINX**: Most popular, high-performance, open-source
- **HAProxy**: Reliable, feature-rich
- **Apache HTTP Server**: With mod_proxy_balancer module

### Cloud Load Balancers
- **AWS**: Elastic Load Balancer (Application Load Balancer, Network Load Balancer)
- **Google Cloud**: Cloud Load Balancing
- **Microsoft Azure**: Azure Load Balancer

## Key Considerations

### Health Checks
Load balancers continuously monitor server health through periodic checks to ensure traffic only goes to healthy servers.

### Session Persistence (Sticky Sessions)
When user session data is stored on a specific server, the load balancer must route subsequent requests from that user to the same server.

### SSL Termination
Offloading SSL/TLS decryption at the load balancer to reduce computational burden on application servers.
