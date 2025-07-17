
# 🧰 Troubleshooting Scenarios & CLI Tools – IT Support Lab

This document outlines real-world troubleshooting scenarios paired with command-line tools used during my network and systems administration lab. These cases reflect typical issues encountered in enterprise environments, and how they were diagnosed and resolved using built-in tools.

---

## ⚙️ Core CLI Tools

| Tool         | Purpose                                      | Example                         |
|--------------|----------------------------------------------|----------------------------------|
| `ping`       | Test connectivity between devices            | `ping 192.168.1.1`               |
| `tracert`    | Trace path to remote host (Windows)          | `tracert google.com`            |
| `traceroute` | Trace path to remote host (Linux)            | `traceroute google.com`         |
| `ipconfig`   | View IP, gateway, DNS (Windows)              | `ipconfig /all`                 |
| `ifconfig`   | View IP details (Linux)                      | `ifconfig`                      |
| `nslookup`   | DNS resolution testing                       | `nslookup google.com`           |
| `netstat`    | View open connections, ports                 | `netstat -ano`                  |
| `arp -a`     | View MAC/IP mappings                         | `arp -a`                        |
| `nmap`       | Scan open ports on a host                    | `nmap 192.168.1.10`             |
| `route print`| Display routing table (Windows)              | `route print`                   |

---

## 🧪 Common Troubleshooting Scenarios

### 🔌 Scenario 1: Client Can't Access the Internet

**Symptoms:**
- Can’t ping `8.8.8.8`
- DNS requests fail

**Diagnosis:**
- `ipconfig` shows missing or incorrect gateway

**Fix:**
- Re-added correct default gateway via `ipconfig` or network settings

---

### 🌐 Scenario 2: DNS Resolution Fails

**Symptoms:**
- IP pings work, domain names do not
- `ping google.com` fails, but `ping 8.8.8.8` succeeds

**Diagnosis:**
- `nslookup` shows DNS timeouts

**Fix:**
- Corrected DNS to use pfSense or public resolver (1.1.1.1)

---

### 🖥️ Scenario 3: Client Can’t Reach Server

**Symptoms:**
- No response from `ping 192.168.1.10`
- Client can ping router

**Diagnosis:**
- Firewall enabled on server, blocking ICMP

**Fix:**
- Allowed ICMP Echo on server via Windows Defender Firewall

---

### 🔁 Scenario 4: IP Conflict on Network

**Symptoms:**
- Client keeps disconnecting
- DHCP assigns same IP to two devices

**Diagnosis:**
- `arp -a` shows duplicate MACs

**Fix:**
- Reserved IPs in DHCP pool and cleared conflict

---

### 🖧 Scenario 5: Inter-VLAN Routing Fails

**Symptoms:**
- Clients on VLAN 10 can't reach VLAN 20

**Diagnosis:**
- pfSense firewall rules missing

**Fix:**
- Added inter-VLAN allow rule in pfSense

---

## 📌 Documentation Style

Each issue was tracked using GLPI with:
- Title
- Description
- Commands used
- Screenshots (before/after)
- Resolution and verification steps

---

## ✅ Outcomes

This section of the lab builds strong foundations in:
- Real-world troubleshooting flow
- Core CLI tools usage
- Fast diagnosis under pressure

Used in conjunction with ticketing (GLPI) and infrastructure (pfSense, VMware, Windows Server/Client).

