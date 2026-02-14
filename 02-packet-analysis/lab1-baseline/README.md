# Lab 1 – Baseline Network Traffic Analysis

## Objective
Capture and analyse normal network traffic to build an understanding of standard request and response behaviour during everyday web browsing.

## Environment
- Host OS: Windows
- Tool: Wireshark
- Network: Home network

## Activity Performed
- Captured live network traffic using Wireshark
- Visited example.com and wikipedia.org during the capture
- Observed DNS resolution, TCP connection setup, and HTTPS traffic

## Key Observations
- A DNS query for www.wikipedia.org was observed with a unique Transaction ID, which identifies the request.
- The matching DNS response was correlated using the same Transaction ID, confirming successful domain resolution.
- DNS resolution occurred before any TCP connection was established, which aligns with normal web traffic behaviour.

- A TCP three-way handshake was observed prior to HTTPS communication.
- The handshake consisted of a SYN packet from the client, a SYN/ACK response from the server, and a final ACK from the client.
- Successful completion of the handshake confirmed that a reliable TCP connection was established before encrypted data transfer began.

## Evidence
The screenshots below show the DNS query and response, followed by the TCP three-way handshake observed during the same browsing session.

### DNS Resolution
![DNS Query](screenshots/dns-query.png)
![DNS Response](screenshots/dns-response.png)

### TCP Three-Way Handshake
![TCP SYN](screenshots/tcp-syn.png)
![TCP SYN-ACK](screenshots/tcp-synack.png)
![TCP ACK](screenshots/tcp-ack.png)

## Outcome
This lab establishes a baseline understanding of normal DNS and TCP behaviour during web browsing. Having this baseline is essential before analysing traffic that may indicate misconfiguration, abnormal activity, or malicious behaviour.
