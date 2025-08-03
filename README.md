#  Behavioral Baseline Detection (SOC Project)

##  Project Overview
This project focuses on detecting unusual user activity in enterprise environments by creating behavioral baselines. Instead of relying solely on static rules, this detection approach monitors what’s *normal* for each user—like which files they access or when they typically log in—and then alerts when behavior deviates significantly from that baseline.

It's designed to catch early signs of insider threats, compromised accounts, or lateral movement attempts by looking at behavioral outliers.

---

##  Goals
- Detect when a user accesses files abnormally often or accesses unfamiliar files.
- Identify logons that happen during unusual hours for a specific user.
- Prioritize alerts using a risk scoring model to reduce alert fatigue and false positives.

---

##  Detection Phases

###  Phase 1: Abnormal File Access Detection
In this phase, we establish a baseline for how often users typically access specific files. When a user accesses a file significantly more frequently than their usual behavior, it’s flagged as potentially suspicious. This is useful for spotting:
- Data exfiltration
- Compromised insider accounts
- Abnormal access to sensitive directories

---

###  Phase 2: Rare Hourly Logon Detection
Here we analyze when users typically log into systems. If someone logs in during a time they almost never do—like 2:00 AM—it might indicate unauthorized activity or an attacker working off-hours to avoid detection.

---

###  Phase 3: Risk Scoring and Alert Prioritization
Both detections are weighted and combined into a risk score. Users with higher risk scores are prioritized for investigation. This approach helps SOC analysts focus on truly anomalous behavior instead of one-off events.

---

##  Techniques Used
- Behavioral baselining per user
- Anomaly detection using statistical thresholds
- Risk-based scoring for alert prioritization
- Time-series behavior modeling

---

##  MITRE ATT&CK Mapping (General)
- **T1078**: Valid Accounts
- **T1087**: Account Discovery
- **T1005**: Data from Local System

---

## 💻 Tools & Technologies
- **Splunk** (Search Processing Language - SPL)
- Synthetic data simulation (for safe testing)
- CSV lookups and baseline modeling

---


## 📝 Notes
This project was built as part of a SOC detection engineering portfolio. It demonstrates how behavioral analytics and baselining can detect subtle, low-noise security incidents that often evade traditional alerting.

