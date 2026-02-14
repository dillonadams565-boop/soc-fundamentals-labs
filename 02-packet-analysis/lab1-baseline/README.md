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

## Evidence
The screenshots below show the DNS query and its corresponding response, linked using the Transaction ID field.

![DNS Query](screenshots/dns-query.png)
![DNS Response](screenshots/dns-response.png)

## Outcome
This lab establishes a clear baseline of what normal DNS behaviour looks like. Understanding this baseline is important before attempting to identify abnormal or potentially malicious network activity.
