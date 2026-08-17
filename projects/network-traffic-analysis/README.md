# Cybersecurity Incident Report — Network Traffic Analysis

## Project Overview

This project involved investigating a simulated network connectivity incident as part of the Google Cybersecurity Professional Certificate.

The investigation focused on analysing DNS and ICMP network traffic to identify why users were unable to access a company's website.

The analysis identified an issue involving DNS traffic on port 53 and considered possible causes including firewall misconfiguration and a potential denial-of-service attack against the DNS server.

## Incident Summary

Several customers reported that they were unable to access the company's website and received a "destination port unreachable" error.

The network security team investigated the incident using `tcpdump` to analyse network traffic.

The investigation showed that DNS traffic using UDP port 53 was unreachable.

Because DNS commonly uses port 53 to resolve domain names, the issue prevented users from successfully reaching the website.

## Key Findings

- UDP port 53 was unreachable.
- ICMP traffic returned a "UDP port 53 unreachable" error.
- Port 53 is used for DNS services.
- The incident prevented users from accessing the company's website.
- Network traffic analysis was performed using `tcpdump`.

## Possible Causes

Two potential causes were identified during the investigation:

1. **Firewall misconfiguration**

   A firewall rule may have been incorrectly configured to block DNS traffic on port 53.

2. **Potential DoS/DDoS attack**

   The DNS server may have been experiencing malicious traffic that affected its availability.

Further investigation would be required to determine the exact root cause.

## Investigation Process

The investigation followed a basic incident-response process:

1. Customers reported that the website was unavailable.
2. The network security team began investigating the issue.
3. `tcpdump` was used to capture and analyse network traffic.
4. The captured traffic was reviewed for errors and affected ports.
5. UDP port 53 was identified as unreachable.
6. Possible firewall and DNS-server issues were considered.
7. Further investigation of firewall rules and DNS-server activity was recommended.

## Recommended Next Steps

- Review firewall rules affecting UDP port 53.
- Confirm that legitimate DNS traffic is permitted.
- Check the DNS server for signs of malicious activity.
- Investigate potential DoS/DDoS traffic.
- Continue monitoring network traffic for similar errors.
- Confirm that DNS services are functioning correctly after remediation.

## Skills Demonstrated

- Network traffic analysis
- DNS fundamentals
- ICMP analysis
- UDP and port analysis
- `tcpdump`
- Incident investigation
- Troubleshooting
- Identifying potential security threats
- Incident-response documentation

## Tools & Technologies

- Linux
- `tcpdump`
- DNS
- ICMP
- UDP
- Network protocol analysis

## Project Context

This was a simulated cybersecurity incident completed as part of the Google Cybersecurity Professional Certificate.

The project demonstrates my ability to analyse network traffic, identify potential causes of a security incident, document findings, and recommend appropriate next steps.