
# 🪟 Windows Server + Client Install Guides (VMware Workstation)

This guide documents how I installed and configured both **Windows Server 2022** and **Windows 10 Pro** virtual machines using **VMware Workstation** for use in my IT Support Lab.

---

## 🧱 VM Settings Summary

| VM Type           | RAM   | CPUs | Disk | Network  | ISO Used                         |
|------------------|-------|------|------|----------|----------------------------------|
| Windows Server 22 | 2 GB  | 2    | 60GB | VMnet3 (custom) | Windows Server 2022 ISO |
| Windows 10 Pro    | 2 GB  | 2    | 60GB | VMnet3 (custom) | Windows 10 Pro ISO       |

---

## 📥 Step 1: Create Virtual Machine

1. Open **VMware Workstation**
2. Click **Create a New Virtual Machine**
3. Choose **Typical (Recommended)** → Next
4. Select **Installer disc image file (ISO)** → Browse for your Windows ISO
5. Follow prompts:
   - Set OS name and location
   - Allocate 60GB of storage
   - Choose **Split virtual disk into multiple files**
   - Finish creation

---

## ⚙️ Step 2: Configure VM Settings (Before Powering On)

Adjust these under **Edit virtual machine settings**:

### 💾 Memory (RAM)
- Set to: **2 GB (2048 MB)**
- Matches recommended minimum for Server 2022 and Win 10

### 🧠 Processors
- Number of processors: `1`
- Number of cores per processor: `2`

### 💽 Hard Disk
- Size: **60 GB**
- Disk type: NVMe or SATA (default works fine)

### 🌐 Network Adapter
- Set to: **Custom: VMnet3**
- Used for internal lab network with pfSense or isolated traffic

### 📀 CD/DVD (ISO)
- Mounted to: `Windows Server 2022` or `Windows 10` ISO
- Option: "Connect at power on" ✅

---

## 🚀 Step 3: Power On & Begin Installation

### Windows Server 2022:
1. Boot into ISO
2. Choose **Standard Edition (GUI)** if applicable
3. Partition disk, follow installer
4. Set password for local admin

### Windows 10 Pro:
1. Boot into ISO
2. Choose **Custom install**
3. Partition disk, install
4. Skip Microsoft account login (use offline account)

---

## 🧪 Post-Install Setup

After first boot:

### Windows Server:
- Rename computer
- Enable RDP (Remote Desktop)
- Join domain (if DC is configured)
- Configure static IP (optional)
- Install roles/features via Server Manager

### Windows 10:
- Rename PC
- Set static IP (optional)
- Join domain
- Enable RDP
- Configure user accounts

---


## ✅ Outcome

Both virtual machines are successfully installed and configured as part of my IT support lab. They're used for:

- Active Directory (Server)
- Domain joining & policy testing (Client)
- Helpdesk ticketing scenarios
- RDP/remote access simulation
