# task2-EL-

# OS-Level Security & Hardening Project

## 🛡️ Project Overview
This project demonstrates essential Operating System hardening techniques performed on an **Ubuntu 24.04 LTS** virtual environment. The goal was to reduce the system's attack surface, implement strict access controls, and ensure a "Deny by Default" network posture.

## 🛠️ Tools & Environment
* **Primary OS:** Ubuntu Linux (Running on VirtualBox)
* **Security Tools:** UFW (Uncomplicated Firewall), Systemd, Bash, GNU Coreutils
* **Target:** Implementation of the Principle of Least Privilege (PoLP)

## 🚀 Hardening Implementation

### 1. System Patching & Updates
Ensured the system is resilient against known vulnerabilities (CVEs) by automating security patches.
* **Action:** Configured `unattended-upgrades`.
* **Benefit:** Reduces the window of opportunity for exploits targeting unpatched software.

### 2. Network Security (Firewall)
Implemented a strict firewall policy using **UFW**.
* **Policy:** Default Deny Incoming / Default Allow Outgoing.
* **Action:** Only essential ports (e.g., SSH) were explicitly opened.
* **Benefit:** Prevents unauthorized external connections and hides unused open ports from network scanners.

### 3. Filesystem Security
Secured sensitive data by managing Linux file permissions and ownership.
* **Action:** Used `chmod 600` on sensitive configuration files.
* **Command:** `ls -l ~/sensitive_data.txt`
* **Result:** Verified `-rw-------` permissions, ensuring only the file owner can access the content.

### 4. Attack Surface Reduction
Audited and disabled unnecessary background services that could serve as entry points for attackers.
* **Action:** Identified listening ports using `ss -tulpn` and disabled the `cups` (printing) service.
* **Benefit:** Fewer running services mean fewer potential bugs or misconfigurations for an attacker to exploit.

### 5. Access Control & Privileges
* **Action:** Verified `sudo` group membership and locked the root account.
* **Benefit:** Prevents direct root login, forcing the use of `sudo` which creates an audit trail for administrative actions.

## 📄 Project Deliverables
* **Hardening Script:** Located in `/scripts/hardening process.sh`
* **Security Checklist:** Comprehensive audit of all applied security controls.

## 🏁 Final Outcome
Successfully transformed a "stock" OS installation into a hardened environment. This lab provided a deep understanding of how configuration-level changes can significantly increase the "cost of attack" for an adversary.
