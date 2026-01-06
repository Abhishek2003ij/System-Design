# TCP vs UDP – Detailed Comparison

## TCP (Transmission Control Protocol)

### What it is
TCP is a **connection-oriented** protocol used for reliable communication between devices over a network.

### How it works
Before data transfer begins, TCP establishes a connection using a **three-way handshake**:
1. SYN
2. SYN-ACK
3. ACK

Data is then sent in **ordered packets**. Each packet is acknowledged by the receiver.  
If any packet is lost, TCP **retransmits** it.

### Key features
- Reliable data transfer
- Guaranteed packet delivery
- Maintains packet order
- Error detection and correction
- Flow control and congestion control

### Advantages
- No data loss
- Data arrives in correct order
- Ideal for critical data

### Disadvantages
- Slower due to overhead
- Higher latency
- Not suitable for real-time applications

### Common uses
- Web browsing (HTTP/HTTPS)
- Email (SMTP, POP3, IMAP)
- File transfer (FTP, SFTP)
- Remote login (SSH)

---

## UDP (User Datagram Protocol)

### What it is
UDP is a **connectionless** protocol that sends data without establishing a connection.

### How it works
Data is sent as independent packets called **datagrams**.  
There is **no handshake**, no acknowledgment, and no retransmission.

### Key features
- Fast transmission
- No guarantee of delivery
- Packets may arrive out of order
- Minimal overhead

### Advantages
- Very fast
- Low latency
- Ideal for real-time communication

### Disadvantages
- Packet loss possible
- No guarantee of order
- No congestion control

### Common uses
- Video streaming
- Online gaming
- Voice over IP (VoIP)
- DNS queries
- Live broadcasts

---

## Key Differences (Simple Terms)

| Aspect | TCP | UDP |
|------|-----|-----|
| Connection type | Connection-oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Speed | Slower | Faster |
| Packet order | Maintained | Not guaranteed |
| Error handling | Yes | No |
| Handshake | Required | Not required |
| Overhead | High | Low |
| Use cases | Web, email, file transfer | Streaming, gaming, VoIP |

---

## Analogy

- **TCP**: Sending a registered courier with tracking and confirmation
- **UDP**: Shouting information and hoping the listener hears it

---

## Bottom Line
Use **TCP** when **accuracy and reliability** matter.  
Use **UDP** when **speed and low latency** are more important than reliability.
