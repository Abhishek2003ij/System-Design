# IP Addresses

## Definition
IP Addresses (Internet Protocol Addresses) are unique numerical identifiers assigned to each device connected to a network that uses the Internet Protocol for communication. They serve two main functions: identifying the host or network interface and providing the location of the host in the network

## Why IP Addresses are Essential
- **Device Identification**: Uniquely identifies each device on a network
- **Network Routing**: Enables data packets to reach correct destinations
- **Network Segmentation**: Allows organizing devices into logical groups
- **Security Implementation**: Basis for access control and firewall rules
- **Troubleshooting**: Essential for network diagnostics and monitoring

## IP Address Versions

### IPv4 (Internet Protocol Version 4)
**Format**: 32-bit address, represented as four decimal numbers separated by dots
**Example**: `192.168.1.1`
**Total Addresses**: Approximately 4.3 billion (2³²)
**Notation**: Dotted-decimal notation (0-255 per octet)

### IPv6 (Internet Protocol Version 6)
**Format**: 128-bit address, represented as eight groups of four hexadecimal digits
**Example**: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
**Total Addresses**: Approximately 3.4 × 10³⁸ (virtually unlimited)
**Notation**: Hexadecimal notation, can be compressed (remove leading zeros, replace consecutive zeros with ::)

## IPv4 Address Classes

### Class A Addresses
**Range**: `1.0.0.0` to `126.255.255.255`
**Network/Host Bits**: 8 network bits, 24 host bits
**Subnet Mask**: `255.0.0.0` or `/8`
**Use Case**: Very large networks, government agencies

### Class B Addresses
**Range**: `128.0.0.0` to `191.255.255.255`
**Network/Host Bits**: 16 network bits, 16 host bits
**Subnet Mask**: `255.255.0.0` or `/16`
**Use Case**: Large organizations, universities

### Class C Addresses
**Range**: `192.0.0.0` to `223.255.255.255`
**Network/Host Bits**: 24 network bits, 8 host bits
**Subnet Mask**: `255.255.255.0` or `/24`
**Use Case**: Small businesses, home networks

### Special Address Ranges
**Private IP Ranges**:
- `10.0.0.0` to `10.255.255.255` (Class A private)
- `172.16.0.0` to `172.31.255.255` (Class B private)
- `192.168.0.0` to `192.168.255.255` (Class C private)

**Loopback Address**: `127.0.0.1` (localhost)
**APIPA**: `169.254.0.0` to `169.254.255.255` (Automatic Private IP Addressing)

## Subnetting

### What is Subnetting?
The process of dividing a network into smaller, more manageable subnetworks (subnets).

### Subnet Mask
A 32-bit number that masks an IP address and divides it into network and host portions.

**Common Subnet Masks**:
- `/24` = `255.255.255.0` = 256 addresses
- `/25` = `255.255.255.128` = 128 addresses
- `/26` = `255.255.255.192` = 64 addresses
- `/30` = `255.255.255.252` = 4 addresses (2 usable)

### Subnet Calculation Example
**Network**: `192.168.1.0/24`
**Subnet Mask**: `255.255.255.0`
**Total Addresses**: 256
**Usable Addresses**: 254 (excluding network and broadcast)
**Network Address**: `192.168.1.0`
**Broadcast Address**: `192.168.1.255`
**Usable Range**: `192.168.1.1` to `192.168.1.254`

### CIDR Notation
Classless Inter-Domain Routing (CIDR) represents subnet masks as prefix length.
- `/24` = `255.255.255.0`
- `/16` = `255.255.0.0`
- `/8` = `255.0.0.0`

## IP Address Types

### Public IP Address
**Definition**: Globally routable address on the Internet
**Assigned by**: Internet Service Provider (ISP)
**Example**: ISP provides `203.0.113.1` to your router
**Cost**: Usually paid service

### Private IP Address
**Definition**: Non-routable address for internal networks
**Ranges**: Defined in RFC 1918
**Example**: Home router assigns `192.168.1.100` to your laptop
**NAT Required**: Needs Network Address Translation to access Internet

### Static IP Address
**Definition**: Manually configured, doesn't change
**Use Case**: Servers, network devices, VPN endpoints
**Advantage**: Predictable, reliable for services

### Dynamic IP Address
**Definition**: Automatically assigned, can change
**Protocol**: DHCP (Dynamic Host Configuration Protocol)
**Use Case**: Client devices, workstations
**Advantage**: Efficient address management

