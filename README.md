# SOC Center Homelab (Detection, Monitoring & Digital Forensics)

A miniature Security Operations Center (SOC) homelab built in an EVE-NG virtual environment.  
The lab integrates **pfSense** (firewall/router & segmentation), **Security Onion** (IDS/IPS + NSM/log analysis), and **Splunk** (SIEM for centralized log collection, correlation, and dashboards).  
A controlled attack scenario against **Metasploitable2** is used to validate detection, logging, and containment workflows.

---

## Project Overview
This project demonstrates how to design and operate a small SOC environment for practical cybersecurity training.  
It focuses on:
- Building a segmented lab network and enforcing security controls
- Collecting and forwarding logs (syslog + endpoint logs)
- Monitoring traffic and generating detections (IDS/NSM)
- Performing SOC-style investigation using dashboards and searches
- Measuring detection/response effectiveness (KPIs)

---

## Key Components (Tools & Stack)
- **Hypervisor / Lab Platform:** VMware Workstation (or VirtualBox) + **EVE-NG**
- **Firewall & Segmentation:** **pfSense** (interfaces, rules, bridging/SPAN where applicable)
- **Detection & Monitoring:** **Security Onion** (e.g., Suricata, Zeek, Wazuh, Kibana/Hunt)
- **SIEM & Dashboards:** **Splunk Enterprise** (indexes, searches, dashboards)
- **Attack Simulation:** **Kali Linux**
- **Victim/Target:** **Metasploitable2** (and optional DVWA/VulnHub machines)
- **Optional Enterprise Simulation:** Windows Server (AD Domain Controller) + Windows endpoints

---

## Architecture & Topology (High Level)
The environment is segmented into multiple virtual networks:
- Attacker network (Kali)
- Victim network (targets/AD/endpoints)
- Monitoring network (SPAN / mirrored traffic for Security Onion)
- SIEM/logging network (Splunk and log sources)

Traffic is controlled by pfSense, mirrored/observed by Security Onion, and logs are centralized in Splunk for correlation and analysis.

---

## What This Repository Contains
Recommended structure (you can adjust):

