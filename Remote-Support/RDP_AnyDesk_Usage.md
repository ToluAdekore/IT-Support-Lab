# 🖥️ RDP & AnyDesk Usage Lab

This lab demonstrates the use of Remote Desktop Protocol (RDP) and AnyDesk for remote IT support scenarios.

---

## 🔧 Lab Objectives

- Connect to a Windows client via RDP
- Practice secure remote access methods

---

## 🧪 Environment Setup

### Virtual Machines

- Windows Server 2022 (Domain Controller)
- Windows 10/11 Client

---

## 🔑 Prerequisites

- RDP enabled on Windows client
- User added to **Remote Desktop Users** group
- Network connectivity (ping test passed)

---

## 🔗 Part 1: RDP Usage

### ✅ Enable RDP on Client

1. Open **System Properties** > Remote
2. Check **Allow remote connections to this computer**
3. Add domain user to **Remote Desktop Users**

### 🔐 Firewall Configuration

Ensure RDP (TCP 3389) is allowed:
```bash
netsh advfirewall firewall set rule group="remote desktop" new enable=Yes
```

### 💻 Connect via RDP

From IT Admin machine:
```bash
mstsc
```
- Enter client IP (e.g., `192.168.1.50`)
- Enter domain credentials


---

## 🧠 Tips

- Always terminate the session after support is complete
- Log session IDs for auditing
- Disable AnyDesk unattended access unless necessary

---

## ✅ Lab Complete

Document your RDP and AnyDesk sessions with screenshots and log entries.
