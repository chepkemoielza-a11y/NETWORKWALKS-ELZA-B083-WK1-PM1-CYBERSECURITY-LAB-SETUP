<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
</p>

---

## 📌 Project Overview

This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using **Oracle VirtualBox** and **Kali Linux 2026.2**.

The laboratory follows the reference NetworkWalks cybersecurity lab architecture and uses a dedicated **VirtualBox NAT Network** to allow virtual machines to communicate within a controlled environment.

The current Kali Linux virtual machine is configured with a manual IPv4 address of:

```text
10.0.0.2/24
```

The laboratory network is:

```text
10.0.0.0/24
```

The environment is designed to be expanded later by adding additional authorized target and testing machines to the same NAT Network.

---

## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux 2026.2.
- Create a dedicated NAT Network in VirtualBox.
- Configure the NAT Network using the `10.0.0.0/24` address range.
- Configure Kali Linux with a manual IPv4 address.
- Configure the default gateway and DNS server.
- Verify the Kali network interface.
- Test connectivity to the virtual gateway.
- Test Internet connectivity.
- Create a VirtualBox snapshot.
- Document the complete laboratory setup.
- Prepare the environment for future penetration-testing exercises.

---

## 🛡️ Purpose of the Lab

The laboratory provides a controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation
- Linux security practice

⚠️ **Important:** This laboratory should only be used against systems that you own or have explicit permission to test.

---

# 🏗️ Lab Architecture

The laboratory follows the reference NetworkWalks architecture.

The main host operating system is Windows 10, with VirtualBox providing the virtualization environment.

The virtual machines are connected through a dedicated NAT Network named:

```text
NatNetwork
```

The network uses the following IPv4 range:

```text
10.0.0.0/24
```

The current Kali Linux machine uses:

```text
10.0.0.2/24
```

The architecture allows additional virtual machines to be connected to the same NAT Network for future authorized cybersecurity exercises.

![Lab Environment Overview](<tittle -image screenshot.png>)

---

# ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration |
|---|---|
| 🖥️ Host OS | Windows 10 |
| 🧰 Hypervisor | VirtualBox 7.2 |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Name | NatNetwork |
| 📡 IPv4 Network | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| 🔌 Network Interface | eth0 |
| 🔧 Network Connection | Wired connection 1 |
| 📡 DHCP | Enabled |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package when required.

The tool is useful for extracting compressed virtual-machine files before importing them into VirtualBox.

---

## Step 2. Install VirtualBox

Oracle VirtualBox 7.2 was installed on the Windows 10 host operating system.

VirtualBox was selected as the hypervisor because it provides the virtualization platform required to create and manage the cybersecurity laboratory.

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

The network was configured with the following settings:

```text
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP Server:  Enabled
```

![VirtualBox NAT Network Configuration](<network-settings screenshot.png>)

The NAT Network allows virtual machines connected to the same network to communicate with one another while providing network address translation for external connectivity.

This configuration provides a suitable foundation for a multi-machine cybersecurity laboratory.

---

## Step 4. Import Kali Linux

Kali Linux 2026.2 was imported into VirtualBox as the security-testing virtual machine.

The Kali Linux VM was configured to use the previously created NAT Network.

### VirtualBox Network Configuration

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
```

The Kali Linux virtual machine was allocated:

```text
RAM: 2048 MB
```

The Kali Linux desktop environment was successfully started.

![Kali Linux Virtual Machine](<kali- linux screenshot.jpeg>)

---

## Step 5. Configure the Kali Linux Network

The Kali Linux network was configured using NetworkManager.

The active network connection was:

```text
Wired connection 1
```

The network interface was:

```text
eth0
```

IPv4 addressing was configured manually using the following settings:

```text
Method: Manual

Address: 10.0.0.2
Netmask: 24
Gateway: 10.0.0.1

DNS Server: 8.8.8.8
```

![Kali Linux Network Settings](<kali-network-settings screenshot.png>)

The manual configuration gives the Kali Linux VM a consistent IP address that can be referenced during future laboratory exercises.

---

# 🔎 Lab Verification

After completing the network configuration, several verification tests were performed.

These tests were used to confirm:

- The Kali network interface was active.
- The correct IP address was assigned.
- The virtual gateway was reachable.
- Internet connectivity was available.

---

## 1. Verify the IP Address

The following command was executed in the Kali Linux terminal:

```bash
ip a
```

The command displayed the network interfaces and their assigned addresses.

The `eth0` interface was active and had the following IPv4 address:

```text
10.0.0.2/24
```

The interface state was:

```text
UP
```

![Kali IP Address Verification](ip-a%20screenshot.png)

### Result

```text
Interface: eth0
IPv4 Address: 10.0.0.2/24
State: UP
```

This confirmed that Kali Linux was correctly connected to the configured virtual network.

---

## 2. Test the Virtual Gateway

The VirtualBox NAT Network gateway was tested using:

```bash
ping -c 4 10.0.0.1
```

The test produced successful responses.

### Result

```text
4 packets transmitted
4 packets received
0% packet loss
```

This confirmed successful communication between Kali Linux and the VirtualBox NAT Network gateway.

---

## 3. Test Internet Connectivity

Internet connectivity was tested using Google's public DNS server:

```bash
ping -c 4 8.8.8.8
```

The test produced successful responses.

### Result

```text
4 packets transmitted
4 packets received
0% packet loss
```

This confirmed that the Kali Linux virtual machine had outbound Internet connectivity.

![Connectivity Test](ping-test%20screenshot.png)

---

## 4. Test DNS Resolution

DNS resolution can be tested using:

```bash
nslookup networkwalks.com
```

A successful result should return DNS information for the requested domain.

This test can be used to verify that the configured DNS server is working correctly.

---

## 5. Verify Nmap

Nmap can be verified using:

```bash
nmap --version
```

The test produced successful responses.

---

# 📊 Verification Results

| ✅ Test | 🧾 Command | 📌 Result |
|---|---|---|
| IP address | `ip a` | ✅ 10.0.0.2/24 |
| Interface status | `ip a` | ✅ eth0 UP |
| Gateway connectivity | `ping -c 4 10.0.0.1` | ✅ 0% packet loss |
| Internet connectivity | `ping -c 4 8.8.8.8` | ✅ 0% packet loss |
| DNS resolution | `nslookup networkwalks.com` | ✅ succesful |
| Nmap | `nmap --version` | ✅ succesful |
| VM snapshot | VirtualBox Snapshot Manager | ✅ Created |

---

# 📸 Evidence Collected

The following screenshots document the laboratory setup and verification process.

| Screenshot | Description |
|---|---|
| `01-tittle-image screenshot.png` | Reference laboratory architecture |
| `02-network-settings screenshot.png` | VirtualBox NAT Network configuration |
| `03-kali-linux screenshot.png` | Kali Linux virtual machine |
| `04-kali-network-settings screenshot.png` | Kali IPv4 network configuration |
| `05-ip-a screenshot.png` | Kali IP address verification |
| `06-ping-test screenshot.png` | Gateway and Internet connectivity |
| `07-kali-snapshot screenshot.png` | VirtualBox snapshot |

---

# 📸 Network Configuration Evidence

The Kali Linux IPv4 configuration shows:

```text
IPv4 Method: Manual
IP Address: 10.0.0.2
Netmask: 24
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

This confirms that the Kali Linux virtual machine was configured according to the laboratory network design.

![Kali Network Configuration](kali-network-settings%20screenshot.png)

---

# 📸 IP Address Verification

The `ip a` command confirmed that the Kali Linux network interface was active.

The relevant configuration was:

```text
eth0
10.0.0.2/24
UP
```

![IP Address Verification](ip-a%20screenshot.png)

---

# 📡 Connectivity Testing

The gateway connectivity test was performed using:

```bash
ping -c 4 10.0.0.1
```

The result was:

```text
4 packets transmitted
4 received
0% packet loss
```

Internet connectivity was tested using:

```bash
ping -c 4 8.8.8.8
```

The result was:

```text
4 packets transmitted
4 received
0% packet loss
```

These results demonstrate successful connectivity from the Kali Linux VM to both the virtual gateway and the external network.

![Connectivity Tests](ping-test%20screenshot.png)

---

# 📸 VM Snapshot

A VirtualBox snapshot was created after the initial Kali Linux configuration.

The snapshot is named:

```text
My Fresh Kali Linux
```

The VirtualBox Snapshot Manager shows the snapshot and the current state of the virtual machine.

![Kali Linux Snapshot](kali-snapshot%20screenshot.png)

The snapshot provides a recovery point that can be used before performing future experimental or potentially disruptive cybersecurity activities.

---

# 🐞 Problems Encountered & Solutions

## Problem 1. Internet Connectivity After Manual IP Configuration

When manually configuring an IPv4 address in Kali Linux, network connectivity can sometimes be affected by NetworkManager configuration or IPv4 address-detection behavior.

The network connection used in this laboratory was:

```text
Wired connection 1
```

NetworkManager can be used to inspect and manage the connection.

A troubleshooting setting that may be used when necessary is:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

After modifying the configuration, the network connection can be restarted and connectivity can be tested again.

---

## Problem 2. VirtualBox Hardware Virtualization Error

A VirtualBox virtual machine may fail to start when hardware virtualization is disabled in the system firmware.

The general solution is:

1. Restart the computer.
2. Enter the BIOS/UEFI settings.
3. Enable Intel VT-x / hardware virtualization.
4. Save the BIOS/UEFI configuration.
5. Restart the computer.
6. Start the Kali Linux virtual machine again.

Hardware virtualization allows VirtualBox to run the virtual machine efficiently.

---

# 💡 What I Learned

## 1. NAT vs NAT Network

I learned the difference between standard NAT and NAT Network configurations.

A NAT Network allows multiple virtual machines connected to the same network to communicate with each other while also providing external network connectivity.

This makes NAT Network suitable for creating a multi-machine cybersecurity laboratory.

---

## 2. Virtual Machine Networking

I learned how VirtualBox network adapters connect virtual machines to different types of networks.

In this laboratory, Kali Linux was connected to:

```text
NatNetwork
```

using the VirtualBox NAT Network configuration.

---

## 3. IPv4 Addressing

I learned how to configure IPv4 networking manually using:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

I also learned how to verify the configuration using:

```bash
ip a
```

---

## 4. Network Connectivity Testing

I learned how to use the `ping` command to verify connectivity.

The gateway was tested with:

```bash
ping -c 4 10.0.0.1
```

Internet connectivity was tested with:

```bash
ping -c 4 8.8.8.8
```

Both tests returned:

```text
0% packet loss
```

---

## 5. VM Snapshots

I learned the importance of creating a clean VM snapshot before performing potentially disruptive cybersecurity experiments.

The snapshot provides a recovery point that allows the virtual machine to be restored if future experiments affect its configuration.

---

## 6. Cybersecurity Documentation

I learned that documenting a cybersecurity project is an important part of professional security work.

The documentation includes:

- Network configuration
- Commands
- Test results
- Screenshots
- Troubleshooting
- Solutions
- Lessons learned

This makes the laboratory easier to reproduce and demonstrate.

---

# 🔐 Security & Ethical Use

This laboratory is intended strictly for cybersecurity education and authorized security testing.

All reconnaissance, scanning, vulnerability assessment, and exploitation activities should only be performed against:

- Systems owned by the user.
- Virtual machines created specifically for testing.
- Systems for which explicit authorization has been obtained.

Unauthorized scanning or exploitation of third-party systems is not permitted.

---

# 🔗 Tools & Resources

- **7-Zip:** https://7-zip.org/download.html
- **VirtualBox:** https://virtualbox.org/wiki/Downloads
- **Kali Linux:** https://kali.org/get-kali

---

# 👤 Author

**[Elza Chepkemoi]**

Cybersecurity & Networking Lab Project

LinkedIn: **[https://www.linkedin.com/in/rotich-elza-3795ab411?utm_source=share_via&utm_content=profile&utm_medium=member_android]**

---

# 📌 Project Information

| 📌 Item | Details |
|---|---|
| Program | Cybersecurity at NetworkWalks |
| Week | 01 |
| Project | Cybersecurity & Penetration Testing Lab Setup |
| Host OS | Windows 10 |
| Hypervisor | VirtualBox 7.2 |
| Security OS | Kali Linux 2026.2 |
| Virtual Network | NatNetwork |
| Network | 10.0.0.0/24 |
| Kali IP | 10.0.0.2/24 |
| Gateway | 10.0.0.1 |
| DNS | 8.8.8.8 |
| Status | Initial Lab Setup Complete

---

# ✅ Project Status

**Status: Initial Lab Setup Completed**

The Kali Linux cybersecurity laboratory has been successfully configured using VirtualBox and a dedicated NAT Network.

### Current Verified Configuration

```text
VirtualBox Network: NatNetwork
Network:             10.0.0.0/24
Kali Interface:      eth0
Kali IP:             10.0.0.2/24
Gateway:              10.0.0.1
DNS:                  8.8.8.8
DHCP:                 Enabled
Connectivity:         Successful
Gateway Packet Loss:  0%
Internet Packet Loss: 0%
Snapshot:             My Fresh Kali Linux
```

The laboratory is ready for future authorized cybersecurity and penetration-testing exercises.

---

<div align="center">

**🔐 Cybersecurity Lab | Week 01**

**Learning • Practicing • Documenting**

</div>
