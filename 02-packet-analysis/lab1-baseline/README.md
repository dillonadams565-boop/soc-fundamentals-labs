# Lab 1 – Baseline Network Traffic Analysis

## Objective
Capture and analyse normal network traffic to understand standard request/response behaviour.

## Environment
- Host OS: Windows
- Tool: Wireshark
- Network: Home network

## Activity Performed
- Captured live network traffic
- Visited example.com and wikipedia.org during capture
- Observed DNS resolution, TCP handshakes, and HTTPS traffic

## Key Observations
- A DNS query for www.wikipedia.org was observed with a unique Transaction ID, identifying the request.
- The corresponding DNS response was matched using the same Transaction ID, confirming successful domain resolution.
- DNS resolution occurred prior to TCP connection establishment, which is expected behaviour for normal web traffic.

## Evidence

![DNS Query](screenshots/dns-query.png)
![DNS Response](screenshots/dns-response.png)


## Outcome
This lab establishes a baseline understanding of what normal network traffic looks like before analysing suspicious or malicious behaviour.

