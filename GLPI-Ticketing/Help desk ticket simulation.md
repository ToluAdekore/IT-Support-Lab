
# 🧾 Help Desk Ticket Simulation – GLPI

This markdown file documents a complete simulation of an IT Help Desk environment using GLPI. It includes 15 realistic tickets submitted by an HR user and resolved by a technician (`tech`) through a structured support lifecycle.

---

## 🎯 Objectives

- Simulate real-world IT support operations
- Practice triaging, documenting, and resolving user issues
- Showcase technician workflows and documentation skills

---

## 📋 Ticket Summary

| ID | Title                          | Priority | Requester | Status  |
|----|--------------------------------|----------|-----------|---------|
| 1  | Can't access shared drive      | High     | User HR   | Closed  |
| 2  | Email not syncing on Outlook   | Medium   | User HR   | Closed  |
| 3  | Printer not responding         | Medium   | User HR   | Closed  |
| 4  | VPN connection fails           | Medium   | User HR   | Closed  |
| 5  | Computer stuck on login screen | Medium   | User HR   | Closed  |
| 6  | Account locked out             | Medium   | User HR   | Closed  |
| 7  | New employee onboarding        | Medium   | User HR   | Closed  |
| 8  | Request for Zoom installation  | Medium   | User HR   | Closed  |
| 9  | Password reset request         | Medium   | User HR   | Closed  |
| 10 | Monitor not displaying         | Medium   | User HR   | Closed  |
| 11 | Internal app is slow           | Medium   | User HR   | Closed  |
| 12 | Windows updates failing        | Medium   | User HR   | Closed  |
| 13 | Request for remote desktop     | Medium   | User HR   | Closed  |
| 14 | Wi-Fi keeps disconnecting      | Medium   | User HR   | Closed  |
| 15 | Keyboard not working           | Medium   | User HR   | Closed  |

---

## 🧪 Sample Ticket Detail

### 🎫 Ticket #4 – VPN Connection Fails

**Submitted by:** User HR  
**Description:**  
> “I’m working from home and can’t connect to the VPN. It says ‘Authentication failed.’”

**Follow-up:**  
```
Verified credentials and VPN logs. Found client was outdated. Installed updated VPN client, re-imported config, and tested connection.
```

**Resolution:**  
```
VPN client updated and configuration repaired. User able to connect successfully.
```

---

## 🔁 Technician Workflow

Each ticket followed this general process:

1. Assigned to technician `tech`
2. Added follow-up comment (diagnosis + fix)
3. Logged resolution
4. Updated status: New → Processing → Solved → Closed

---

## 📸 Screenshots

See `/GLPI-Ticketing/screenshots/` for full ticket lifecycle images:
- Ticket creation
- Follow-ups added
- Resolution logged
- Solved & closed status

---

## ✅ Outcome

This simulation demonstrates:
- Real-world ticket triage and tracking
- Strong documentation and technician notes
- End-to-end resolution workflows
