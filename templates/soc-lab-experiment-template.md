# [Experiment Title] — SOC Lab & Detection Engineering Note

- **Environment:** [e.g., Ubuntu Elastic Stack + Fleet + Windows Server/Endpoints + Sysmon + Winlogbeat + FortiGate]
- **Objective:** [e.g., Simulate technique X, collect telemetry, and validate detection rule Y]
- **MITRE ATT&CK Mapping:** [Tactic / Technique ID]

---

## 1. Lab Topology & Components

| Component | OS / Version | Role & Agents Installed |
| :--- | :--- | :--- |
| SIEM Server | Ubuntu Linux | Elasticsearch, Kibana, Fleet Server |
| Endpoint / Target | Windows 10/11 or Windows Server | Sysmon, Winlogbeat / Elastic Agent |
| Network Perimeter | FortiGate | Firewall policy, traffic logging |
| Attacker / Test Host | Kali Linux | Authorized simulation of test behavior |

---

## 2. Configuration & Setup Notes

Document exact configurations, agent policies, or Sysmon configuration sections relevant to the experiment:

```xml
<!-- Example: Relevant Sysmon Rule or Winlogbeat / Fleet Configuration -->
```

### Troubleshooting & Operational Notes
- **Issue Encountered:** [Describe any connectivity, certificate, ingestion, or parsing issue]
- **Root Cause:** [Why it happened]
- **Resolution:** [Step-by-step fix applied]

---

## 3. Telemetry Generation (Authorized Simulation)

- **Action Executed:**
  ```powershell
  # Command or action executed in the lab to generate telemetry
  ```
- **Expected System / Network Behavior:** What happens at the OS, process, registry, file-system, or network layer.

---

## 4. Telemetry Analysis & Detection Logic

- **Observed Events (Elasticsearch / Kibana / Wazuh / Splunk):**
  - Event ID / Source: `...`
  - Key Fields Inspected: `process.executable`, `process.command_line`, `parent.process.name`, etc.
- **Query / Detection Rule (KQL / SPL / Sigma):**
  ```yaml
  title: [Detection Rule Title]
  logsource:
    category: process_creation
    product: windows
  detection:
    selection:
      # fields and values
    condition: selection
  ```

---

## 5. Key Takeaways & Limitations

- **Why the Detection Works:** Connection between attacker behavior, OS telemetry, and alert logic.
- **Potential Evasion / Blind Spots:** How an adversary might bypass this specific rule and what additional telemetry could cover that gap.
