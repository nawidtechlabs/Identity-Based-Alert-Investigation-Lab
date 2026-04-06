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

    index=* failed OR failure

**Purpose:**  
Filter logs to isolate authentication failures for investigation.

---

### 2. Identify High-Risk Users

    index=* failed OR failure 
    | stats count by Account_Name 
    | sort -count

**Purpose:**  
Group failed logins by user to identify accounts with abnormal activity.

---

### 3. Prioritize Suspicious Accounts (SOC Triage Simulation)

    index=* failed OR failure 
    | stats count by Account_Name 
    | where count > 100 
    | sort -count

**Purpose:**  
Simulate alert prioritization by focusing on accounts with unusually high failure counts.

---

## 📊 Key Findings
- Identified multiple accounts with high volumes of failed login attempts  
- Detected patterns consistent with potential brute force behavior  
- Prioritized high-frequency accounts for investigation  

---

## 🧠 Analysis
High volumes of failed logins may indicate:
- Brute force attempts  
- Credential stuffing  
- User error or misconfigured services  

To validate findings, further steps would include:
- Reviewing source IP addresses  
- Analyzing login time patterns  
- Comparing behavior against normal user activity  

---

## 🚨 SOC Workflow Simulation
- Log filtering and analysis  
- Alert triage based on event frequency  
- Identification of suspicious accounts  
- Prioritization of high-risk activity  
- Initial investigation and hypothesis generation  

---

## 🛠️ Skills Demonstrated
- Splunk (SPL)  
- Log analysis  
- Security event investigation  
- Alert triage  
- Basic threat detection (identity-based attacks)
