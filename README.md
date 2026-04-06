# 🛡️ Identity-Based Alert Investigation Lab (Splunk)

## 🧠 Objective
Investigate failed authentication activity using Splunk to identify suspicious user behavior and simulate a Tier 1 SOC alert triage workflow.

---

## 🔍 Data Source
- Windows Security Logs (WinEventLog:Security)
- Authentication failure events (Audit Failure)

---

## ⚙️ Queries Used

### 1. Identify Failed Login Events
```spl
index=* failed OR failure
