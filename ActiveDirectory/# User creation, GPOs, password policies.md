# 👥 Active Directory Setup

This section documents the process of promoting a Windows Server 2022 machine to a Domain Controller and configuring core AD services.

---

## ✅ Domain Controller Setup

- **Server renamed to:** `DC01`
- **Static IP address:** `192.168.1.100`
- **Domain:** `toluadekore.local`

### 🛠️ Steps:

1. Installed **Active Directory Domain Services (AD DS)** via Server Manager
2. Promoted server to Domain Controller using the AD wizard
3. Created a new forest: `toluadekore.local`
4. Rebooted and verified domain controller functionality

---

## 🧑‍💼 User and Group Configuration

### 🔹 Organizational Units (OUs) Created:
- `Students`
- `Staff`
- `Admins`

### 👤 Users Created:
| Username  | Full Name        | OU        | Default Password |
|-----------|------------------|-----------|------------------|
| jsmith    | John Smith       | Students  | `P@ssw0rd1`       |
| tmartin   | Tina Martin      | Staff     | `P@ssw0rd1`       |
| ajones    | Alan Jones       | Admins    | `P@ssw0rd1`       |

> All users were configured to **change password at next login**.

---

## 🔐 Password Policy Configurations

Set under **Group Policy → Default Domain Policy**:
- Minimum password length: `8`
- Enforce password history: `5`
- Maximum password age: `30 days`
- Lockout after 3 failed attempts (lockout duration: 15 mins)

---

## 📸 Screenshots (to be added)
- AD Users and Computers view
- OU structure
- User creation confirmation
- Password policy settings

---

## 🧠 Summary

This setup replicates a basic enterprise Active Directory structure with proper organizational units, user management, and password enforcement — a foundational skill for IT support technicians.


