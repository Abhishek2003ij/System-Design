
### PDU (Protocol Data Unit) Names:
- **Layer 7-5**: Data
- **Layer 4**: Segment (TCP) / Datagram (UDP)
- **Layer 3**: Packet
- **Layer 2**: Frame
- **Layer 1**: Bits

## Practical Examples

### Example 1: Sending an Email:
1. **Application**: User composes email in client (Outlook/Gmail)
2. **Presentation**: Email formatted, attachments encoded
3. **Session**: Connection established with email server
4. **Transport**: TCP ensures reliable delivery
5. **Network**: IP routes to destination server
6. **Data Link**: Ethernet frames sent to local router
7. **Physical**: Electrical signals on wire

### Example 2: Loading a Webpage:
1. **Application**: Browser sends HTTP request
2. **Presentation**: SSL/TLS encryption for HTTPS
3. **Session**: Maintains session with cookies
4. **Transport**: TCP manages connection
5. **Network**: IP finds route to web server
6. **Data Link**: Switches forward frames locally
7. **Physical**: Network card transmits signals

## Common Troubleshooting by Layer

### Physical Layer Issues
- Cable unplugged or damaged
- Incorrect cable type (crossover vs straight-through)
- NIC failure
- Power issues

### Data Link Layer Issues
- MAC address conflicts
- VLAN misconfiguration
- Switch port errors
- Duplex mismatch

### Network Layer Issues
- Incorrect IP configuration
- Routing problems
- Firewall blocking traffic
- Subnet mask errors

### Transport Layer Issues
- Port blocked by firewall
- TCP window size problems
- Connection timeout
- Port exhaustion

### Application Layer Issues
- DNS resolution failure
- HTTP error codes
- Authentication problems
- Protocol version mismatch

## Comparison with TCP/IP Model

| OSI Model | TCP/IP Model | Real-World Usage |
|-----------|--------------|------------------|
| 7 Layers | 4 Layers | OSI is theoretical, TCP/IP is practical |
| Strict layering | Flexible layers | TCP/IP dominates actual implementation |
| Developed by ISO | Developed by DARPA | OSI used for education, TCP/IP for implementation |
| Protocol-independent | Protocol-specific | Most modern networks use TCP/IP stack |

## Key Takeaways

1. **Layered Approach**: Each layer has specific responsibilities
2. **Abstraction**: Higher layers don't need to know lower layer details
3. **Interoperability**: Standards enable different systems to communicate
4. **Troubleshooting**: Problems can be isolated to specific layers
5. **Evolution**: While OSI is theoretical, its concepts are fundamental

## Mnemonics to Remember Layers

### Top-Down (Application to Physical):
**Please Do Not Throw Sausage Pizza Away**
- Physical
- Data Link
- Network
- Transport
- Session
- Presentation
- Application

### Bottom-Up (Physical to Application):
**All People Seem To Need Data Processing**
- Application
- Presentation
- Session
- Transport
- Network
- Data Link
- Physical
