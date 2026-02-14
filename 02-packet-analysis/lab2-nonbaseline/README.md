# Lab 2 — Non-Baseline Network Traffic Analysis

## Objective
Identify network traffic patterns that deviate from normal baseline behaviour across DNS, TCP, and TLS using Wireshark.

## Scope
This lab focuses on:
- DNS traffic anomalies
- TCP connection behaviour that differs from normal use
- TLS session characteristics that may appear suspicious compared to typical browsing

## Environment
- Host OS: Windows
- Tool used: Wireshark
- Network: Home network

## Method
Traffic was intentionally generated to create non-baseline patterns. All traffic was captured using Wireshark and analysed to determine how it differs from normal user activity and whether it could be considered suspicious from a SOC perspective.

## DNS Analysis — Non-Baseline Behaviour

### What was done
Repeated DNS lookups were generated to unique, non-existent subdomains using `nslookup` to intentionally produce failed DNS resolution attempts.

### Wireshark Filter
dns

### What was observed
- A high number of DNS queries in a short time period
- Sequential, unique subdomain names (for example `lab2test1.invalid`, `lab2test2.invalid`)
- All queries resulted in `NXDOMAIN` (“No such name”) responses
- Traffic pattern differed significantly from normal browsing, which usually involves repeated queries to known domains

### SOC Interpretation
A burst of NXDOMAIN DNS activity like this could indicate automated or scripted behaviour, misconfigured applications, or potential malware beaconing patterns depending on context. In an enterprise environment, this activity would warrant further investigation.

### Evidence
- [DNS NXDOMAIN burst](screenshots/dns_nxdomain_burst.png)
- [DNS NXDOMAIN response](screenshots/dns_nxdomain_response.png)
- [DNS NXDOMAIN PCAP](pcap/dns_nxdomain_nonbaseline.pcapng)


## Next Steps
Additional non-baseline analysis will be performed for TCP connection behaviour and TLS session characteristics.
