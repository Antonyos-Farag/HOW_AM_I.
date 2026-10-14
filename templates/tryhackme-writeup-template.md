# [Room Name] — Technical Investigation & Write-Up

- **Platform:** TryHackMe
- **Track / Path:** [e.g., SOC Level 2 / Advanced Endpoint Investigation]
- **Category:** [e.g., DFIR / SIEM / Network Traffic Analysis / Endpoint Forensics]
- **Tools Used:** [e.g., Kibana, Wireshark, Sysmon, Volatility, Zimmerman Tools]
- **MITRE ATT&CK Techniques Observed:** [e.g., T1059.001 PowerShell, T1547.001 Registry Run Keys]

---

## 1. Scenario & Objective

Brief description of the scenario, environment, available data sources (logs, PCAP, disk image, memory dump), and the scope of the investigation.

---

## 2. Investigation Methodology

Explain the structured approach used before running queries or commands:
1. Initial hypothesis / triage scope
2. Telemetry and artifact sources examined
3. Timeline reconstruction approach

---

## 3. Step-by-Step Analysis & Evidence

### Finding 1: [Descriptive Title of Event / Phase]
- **Hypothesis / Question:** What are we looking for and why?
- **Query / Command Executed:**
  ```text
  # Exact SIEM query, command, or filter used
  ```
- **Parameter & Logic Explanation:** Explain what each filter, Event ID, or flag does under the hood.
- **Evidence Observed:**
  - Timestamp: `YYYY-MM-DD HH:MM:SS UTC`
  - Source / Host: `...`
  - Key Artifacts (Process, CommandLine, Network Connection, Hash): `...`
- **Analytical Reasoning:** How this evidence confirms or refutes the hypothesis and leads to the next step.

---

## 4. Attack Chain & Timeline Summary

| Timestamp (UTC) | MITRE Tactic / Technique | Host / Source | Observed Activity & Evidence |
| :--- | :--- | :--- | :--- |
| `...` | Initial Access | `...` | `...` |
| `...` | Execution | `...` | `...` |
| `...` | Persistence | `...` | `...` |

---

## 5. Detection Engineering & Defensive Takeaways

- **Telemetry Required:** Which logs or sensors (e.g., Sysmon Event ID 1, 3, 11; Windows Security Event ID 4624, 4688; firewall traffic logs) made this detection possible?
- **Detection Logic / Sigma Concept:** How can defenders reliably alert on this behavior while minimizing false positives?
- **Lessons Learned:** Underlying OS, network, or adversary concepts reinforced by this investigation.
