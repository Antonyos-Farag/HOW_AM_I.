# 2. Cybersecurity Focus, Training & Practical Labs

Cybersecurity is my primary professional direction. I am developing practical skills through structured training, hands-on labs, technical projects, and independent investigation.

---

## Core Areas of Interest

### Defensive Operations & Investigation
- Security Operations Center (SOC) operations
- SOC Analyst and SOC Engineer career paths
- Network Security and Traffic Analysis
- Threat Hunting and Incident Response
- Digital Forensics and Endpoint Investigation
- SIEM monitoring, alert analysis, and security event investigation
- Windows Security, Sysmon, and Linux
- Detection Engineering and security monitoring
- Threat intelligence and adversary behavior

### Offensive Security & Adversary Perspective
- Web Application Security and Penetration Testing
- Red Team fundamentals and offensive security techniques

> **Connecting Offense and Defense:** I am particularly interested in connecting offensive security knowledge with defensive security operations, allowing me to understand both attacker techniques and how defenders can detect and investigate them.

---

## Completed Training & Practical Programs

| Program / Track | Provider / Context | Details & Outcome |
| :--- | :--- | :--- |
| **Network Security Training** | NTI / ITIDA | 90 hours of technical training + 30 hours of soft skills & freelancing training — **Final Grade: 99.5%** |
| **Cisco CyberOps Associate** | NTI & Cisco Networking Academy | Security operations, monitoring, and analysis — **Score: 92/100** |
| **Huawei HCIA-Security V4.0** | Huawei Training | Network and information security fundamentals and implementation |
| **SOC Level 2** | TryHackMe | Hands-on SOC operations, SIEM alert triage, log analysis, and detection workflows |
| **Advanced Endpoint Investigation** | TryHackMe | File-system analysis, Windows/Linux investigations, macOS & mobile investigation concepts, memory forensics, disk-image analysis |
| **Cybersecurity Internship Program** | TIPS Hindawi | **Penetration Testing Track** — Web security and offensive testing methodology |

---

## Practical Technical Scope

- **Monitoring & Network Analysis:** Security monitoring, packet and traffic analysis, and network infrastructure visibility.
- **Forensics & Endpoint Analysis:** File-system analysis, Windows and Linux investigations, macOS and mobile investigation concepts, memory forensics, disk-image analysis, and underlying technical concepts beyond simply using security tools.
- **Detection Engineering & Frameworks:** Windows event analysis, Sigma rules, MITRE ATT&CK mapping, and the relationship between telemetry, attacker behavior, and security alerts.

---

## Tools, Platforms & Lab Environments

### Technologies Studied & Used
- **SIEM, Log Management & XDR:** Elastic Stack (Elasticsearch, Kibana), Elastic Agent, Fleet, Fleet Server, Splunk, Wazuh
- **Endpoint Telemetry & Network Analysis:** Sysmon, Winlogbeat, Wireshark
- **Network Security & Simulation:** FortiGate, Cisco Packet Tracer
- **Offensive Security & Reconnaissance:** Burp Suite, Nmap, Kali Linux
- **Operating Systems:** Windows, Windows Server, Linux environments

### Multi-Component SOC Lab Environment
I have worked on a SOC lab integrating:
- **Ubuntu-based Elastic environment** (Elasticsearch, Kibana, Fleet / Fleet Server)
- **Windows endpoints** and **Windows Server**
- **Sysmon** and **Winlogbeat** for host-level event and telemetry collection
- **FortiGate** for network perimeter security and traffic control

```
+-------------------------------------------------------------------+
|                        SOC Lab Environment                        |
+-------------------------------------------------------------------+
|                                                                   |
|  [ Windows Endpoints ] ---> ( Sysmon + Winlogbeat / Elastic Agent )|
|                                        |                          |
|  [ Windows Server ] ------> ( Sysmon + Winlogbeat / Elastic Agent )|
|                                        |                          |
|  [ FortiGate Firewall ] ---------------+                          |
|                                        v                          |
|                  [ Ubuntu-Based Elastic Stack ]                   |
|             ( Elasticsearch + Kibana + Fleet Server )             |
+-------------------------------------------------------------------+
```

My focus in lab work is building realistic security environments, generating security telemetry, investigating alerts, understanding detection logic, and documenting the results of technical experiments.
