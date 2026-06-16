# DNS and ICMP Traffic Analysis Report

## 🎯 Project Overview
This project involves analyzing a network packet capture (`tcpdump` log) to investigate a sudden service disruption. As part of the incident response team, I inspected DNS and ICMP traffic in transit to identify the affected network protocols, determine the root cause of the outage, and outline remediation steps.

---

## 💻 Network Capture Visual
Below is a screenshot of the packet analysis indicating the network protocol error:

![Network Traffic Capture](tcpdump-pcap.png) 
*Figure 1: tcpdump log showing the DNS traffic*

---

## 📝 Incident Report

### Part 1: Summary of the Problem
An analysis of the network protocol logs revealed that **UDP Port 53 (DNS)** was unreachable when attempting to access the company's website. 

The issue was confirmed through ICMP traffic analysis. The network analysis showed that when outbound requests were sent to the DNS server, the ICMP echo reply returned an error message: 

> `udp port 53 unreachable`

**Potential Root Causes Under Investigation:**
* **Server Misconfiguration/Downtime:** The DNS service daemon may have crashed or stopped running on the host server.
* **Firewall Configuration Error:** A recent firewall rule update may be inadvertently blocking or dropping traffic on Port 53.
* **Malicious Attack:** A Denial of Service (DoS) or targeted exploit may have compromised the server's availability.

### Part 2: Analysis of the Data & Cause
* **Timeline:** The incident occurred this afternoon when customers reported that they could no longer access the company’s website.
* **Triage & Investigation:** The IT and Security team responded immediately. To troubleshoot the root cause, `tcpdump` was used to capture and inspect live network transit traffic. 
* **Findings:** The packet analysis isolated the issue to the transport layer of the OSI model, showing that Port 53 was actively refusing or failing to receive traffic, returning the ICMP "unreachable" flag.

---

## 🛠️ Next Steps
To detect the root cause of the problem, the following actions are being taken:
1. **Firewall Audit:** Inspect firewall configurations to verify if Port 53 traffic has been blocked.
2. **Server Syslog Analysis:** Contact the systems administrator to check the health of the DNS daemon and review system logs for signs of a cyberattack.

---

## 🔗 Report summary documentation
* **Summary Documentation:** [View the summary of the incident Report Document](https://docs.google.com/document/d/1gcAPlRNHe5sycoQNa4ZqZM6Gj3iiDnp9yb7kfEagm4Q/edit?usp=sharing)
