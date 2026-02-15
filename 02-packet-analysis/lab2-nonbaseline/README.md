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

---

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

---

## TCP Analysis — Non-Baseline Behaviour

### What was done
Repeated TCP connection attempts were generated to a destination that was not accepting connections in order to create failed TCP handshakes.

### Wireshark Filter
tcp.flags.syn == 1 && tcp.flags.ack == 0

### What was observed
- Repeated TCP SYN packets from the same source
- Connection attempts occurred close together in time
- No successful TCP handshakes were established
- Multiple SYN retransmissions were observed, indicating failed connections

### SOC Interpretation
Repeated failed TCP connection attempts may indicate port scanning activity, misconfigured applications, or automated behaviour. In an enterprise environment, this type of traffic would warrant further investigation.

### Evidence
- [TCP SYN burst](screenshots/tcp_syn_burst.png)
- [TCP failed connection detail](screenshots/tcp_failed_connection_detail.png)
- [TCP PCAP](pcap/tcp_failed_connections_nonbaseline.pcapng)

---

## Next Steps
Additional non-baseline analysis will be performed for TLS session characteristics.
