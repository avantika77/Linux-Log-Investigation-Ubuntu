# Linux Log Investigation (Ubuntu)

> **Digital Forensics & Incident Response (DFIR) Project**

---

## Overview

This project demonstrates a Linux Digital Forensics investigation performed on an **Ubuntu Virtual Machine**. The investigation focuses on analyzing authentication logs, system logs, user activity, administrative actions, and preserving forensic evidence.

The objective is to identify security-relevant events, reconstruct an event timeline, and document the investigation using industry-standard DFIR practices.

---

## Objectives

- Collect Linux system information
- Analyze authentication logs
- Investigate user login activity
- Examine sudo privilege usage
- Review CRON scheduled tasks
- Analyze system logs
- Reconstruct an event timeline
- Preserve forensic evidence
- Verify evidence integrity using SHA-256 hashing

---

# Lab Environment

| Component | Details |
|------------|---------|
| Operating System | Ubuntu |
| Virtualization | Oracle VirtualBox |
| Investigation Type | Linux Log Investigation |
| Primary Log | `/var/log/auth.log` |
| Shell | Bash |
| Hash Algorithm | SHA-256 |

---

# Tools Used

- Ubuntu Terminal
- grep
- cat
- tail
- last
- who
- awk
- sha256sum
- Oracle VirtualBox

---

# Investigation Workflow

```text
Environment Setup
        │
        ▼
Evidence Collection
        │
        ▼
Authentication Log Analysis
        │
        ▼
Timeline Reconstruction
        │
        ▼
Evidence Preservation
        │
        ▼
    Reporting
```

---

# Investigation Steps

## Step 1 – Environment Setup

Collected the following system information:

- Hostname
- Current User
- Ubuntu Version
- Kernel Version
- Investigation Date & Time

---

## Step 2 – Log Directory Analysis

Examined the Linux log directory:

```text
/var/log
```

Important log files identified:

- auth.log
- syslog
- dpkg.log
- kern.log

---

## Step 3 – Authentication Log Analysis

Investigated:

```text
/var/log/auth.log
```

Analyzed:

- User login events
- Authentication attempts
- sudo activity
- CRON sessions

---

## Step 4 – Authentication Event Investigation

Filtered security-related events using Linux command-line tools.

Investigated:

- Failed authentication attempts
- Successful authentication
- sudo command execution
- Login activity
- CRON jobs

---

## Step 5 – Timeline Reconstruction

Created an authentication timeline including:

- Login events
- Failed authentication attempts
- sudo execution
- CRON activity

---

## Step 6 – User Investigation

Reviewed:

- Local user accounts
- Active users
- Login history
- User privileges

---

## Step 7 – System Log Analysis

Reviewed:

- syslog
- kernel logs
- package installation history

---

## Step 8 – Evidence Preservation

Collected forensic artifacts and preserved evidence by generating SHA-256 hashes to ensure integrity.

---

# Screenshots/
├── 01_environment_setup.png

├── 02_var_log_directory.png

├── 03_auth_log.png

|── 04_auth_analysis.png

├── 05_authentication_events.png

├── 06_timeline.png

├── 07_user_accounts.png

├── 08_system_logs.png

├── 09_evidence_collection.png

└── 10_hash_verification.png
```

---

# Key Findings

- Successfully collected Linux forensic evidence.
- Authentication logs were analyzed.
- Normal login activity was identified.
- CRON jobs executed successfully.
- One failed sudo authentication attempt was observed.
- Administrative command execution was verified.
- No unauthorized user accounts were identified.
- Evidence integrity was verified using SHA-256 hashing.

---

# Commands Used

Examples of commands used during the investigation:

```bash
hostname
whoami
uname -r
cat /etc/os-release

cd /var/log
ls -lh

sudo tail -20 auth.log

grep "authentication failure" /var/log/auth.log
grep "COMMAND=" /var/log/auth.log
grep "CRON" /var/log/auth.log

cat /etc/passwd
who
last

tail -30 /var/log/syslog
tail -30 /var/log/kern.log

sha256sum evidence/logs/*
```

---

# Skills Demonstrated

- Linux Administration
- Linux Log Analysis
- Digital Forensics
- Incident Response
- Authentication Analysis
- Timeline Reconstruction
- Evidence Preservation
- SHA-256 Hash Verification
- Technical Documentation

---

# Repository Structure

```text
Linux-Log-Investigation-Ubuntu/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── report/
├── evidence/
├── screenshots/
└── commands/
```

---

# Screenshots

The repository includes screenshots demonstrating:

- Environment Setup
- Linux Log Directory
- Authentication Log Analysis
- Authentication Events
- Timeline Reconstruction
- User Investigation
- System Log Analysis
- Evidence Collection
- SHA-256 Verification

---

# Future Improvements

- Automate log parsing using Bash scripts
- Integrate Splunk SIEM
- Investigate Windows Event Logs
- Perform Memory Forensics using Volatility
- Develop automated forensic reporting

---

# Author

**Avantika Shrivastava**

Digital Forensics Enthusiast

---

## License

This project is licensed under the MIT License.
