# Ubuntu Server Deployment & Administration

### Virtualization | Linux Administration | Networking | Remote Access | Web Server | Firewall

## 1. Project Overview

This project simulates a Junior System Administrator task in a virtual company environment called **PT Digital Nusantara**.

The project focuses on deploying and managing an Ubuntu Server environment, configuring network connectivity, enabling remote administration, hosting a static website using Nginx, and implementing basic firewall rules using UFW.

The project was performed using Oracle VirtualBox with Ubuntu Server 22.04.2 LTS.

## 2. Project Objectives

- Install Ubuntu Server in a virtual machine.
- Configure server identity and network connectivity.
- Establish communication between the server and Windows host.
- Enable remote server administration using OpenSSH.
- Install and deploy a website using Nginx.
- Configure firewall rules using UFW.
- Perform service validation and connectivity testing.
- Troubleshoot package management issues.

## 3. Infrastructure Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Operating System | Ubuntu Server 22.04.2 LTS |
| Virtual Memory | 2 GB RAM |
| Virtual CPU | 2 Processors |
| Virtual Disk | 20 GB |
| Network Adapter | Bridged Adapter |
| Hostname | ubuntu-webserver |
| Server IP | 192.168.100.246/24 |
| Default Gateway | 192.168.100.1 |

### Services & Technologies

| Technology | Purpose |
|---|---|
| Ubuntu Server | Server operating system |
| VirtualBox | Virtualization platform |
| OpenSSH | Remote server administration |
| Nginx | Web server |
| UFW | Firewall management |
| APT / DPKG | Package management |
| HTML / CSS | Static website content |

## 4. Network Architecture

The server uses a Bridged Adapter to communicate with the Windows host through the local network.

```text
+-----------------------------+
|       Windows 11 Host       |
|     Administrator Client    |
+--------------+--------------+
               |
               | Local Network
               |
+--------------v--------------+
|         VirtualBox          |
|                             |
|   +---------------------+   |
|   |    Ubuntu Server    |   |
|   |                     |   |
|   | Ubuntu 22.04.2 LTS  |   |
|   | IP: 192.168.100.246 |   |
|   |                     |   |
|   | OpenSSH : TCP 22    |   |
|   | Nginx   : TCP 80    |   |
|   | UFW Firewall        |   |
|   +---------------------+   |
+-----------------------------+
```

### Network Configuration

| Parameter | Value |
|---|---|
| Server IP | 192.168.100.246 |
| Subnet Mask | /24 |
| Gateway | 192.168.100.1 |
| Network Mode | Bridged |

## 5. Implementation & Configuration

### Step 1 — Ubuntu Server Installation

Created a virtual machine in VirtualBox and installed Ubuntu Server 22.04.2 LTS.

Configuration included:
- 2 GB RAM.
- 2 virtual processors.
- 20 GB virtual disk.
- Ubuntu Server standard installation.
- Guided storage configuration with LVM.
- Server hostname configuration.

### Step 2 — Server Identity Verification

Verified the operating system and server hostname.

```bash
hostnamectl
```

### Step 3 — Network Configuration & Testing

Checked the network interface and IP configuration.

```bash
ip a
ip route
```

Tested connectivity to the local gateway.

```bash
ping -c 4 192.168.100.1
```

Also performed a ping test from Windows to Ubuntu Server.

**Result:** 3 packets received with 0% packet loss.

### Step 4 — OpenSSH Installation & Troubleshooting

During OpenSSH installation, a DPKG interruption issue was encountered.

Resolved the package configuration issue using:

```bash
sudo dpkg --configure -a
```

Installed OpenSSH:

```bash
sudo apt install openssh-server -y
```

Enabled and started the SSH service:

```bash
sudo systemctl enable --now ssh
```

Verified the service:

```bash
sudo systemctl status ssh
```

**Result:** Remote administration from Windows was successfully established.

### Step 5 — Nginx Installation

Installed Nginx using APT.

```bash
sudo apt install nginx -y
```

Enabled Nginx to start automatically during system boot.

```bash
sudo systemctl enable --now nginx
```

Checked the service status:

```bash
sudo systemctl status nginx
```

**Result:** Nginx service successfully entered the active (running) state.

### Step 6 — Website Deployment

Used the default Nginx web root directory:

```text
/var/www/html
```

Created a backup of the default Nginx welcome page before replacing the website content.

Created and edited the website file:

```bash
sudo nano /var/www/html/index.html
```

Deployed a static company profile website for the simulated organization **PT Digital Nusantara**.

The website presents the company's digital infrastructure services.

**Result:** The website was successfully displayed through a Windows web browser using the server's local IP address.

### Step 7 — Quality Assurance

Tested the HTTP response:

```bash
curl -I http://localhost
```

Validated the Nginx configuration:

```bash
sudo nginx -t
```

**Verified results:**
- HTTP response: `HTTP/1.1 200 OK`
- Nginx configuration: `syntax is ok`
- Configuration test: `test is successful`

### Step 8 — UFW Firewall Configuration

Configured UFW to restrict SSH and HTTP access to the local network subnet.

Allowed SSH access from the local subnet:

```bash
sudo ufw allow from 192.168.100.0/24 to any port 22 proto tcp
```

Allowed HTTP access from the local subnet:

```bash
sudo ufw allow from 192.168.100.0/24 to any port 80 proto tcp
```

Enabled the firewall:

```bash
sudo ufw enable
```

Verified firewall configuration:

```bash
sudo ufw status verbose
```

**Result:** UFW was successfully enabled with restricted SSH and HTTP access rules.

### Step 9 — Post-Firewall Validation

After enabling UFW, performed additional tests to ensure that essential services remained accessible.

Validation included:
- SSH remote login from Windows.
- Website accessibility through a browser.
- Nginx service availability.

**Result:** SSH and HTTP services remained accessible after firewall activation.

## 6. Troubleshooting Experience

| Issue | Resolution |
|---|---|
| DPKG configuration interrupted | Executed `sudo dpkg --configure -a` |
| OpenSSH installation issue | Reconfigured DPKG and repeated installation |
| Network connectivity verification | Used `ip a`, `ip route`, and `ping` |
| Nginx service verification | Used `systemctl status nginx` |
| Website response verification | Used `curl -I` |

This project provided practical experience in identifying and resolving basic Linux server administration issues.

## 7. Testing & Validation Results

| Test | Result |
|---|---|
| Ubuntu Server Installation | Successful |
| Server Network Connectivity | Successful |
| Windows-to-Server Ping | 0% Packet Loss |
| OpenSSH Remote Access | Successful |
| Nginx Service | Active (Running) |
| Website Deployment | Successful |
| HTTP Response | 200 OK |
| Nginx Configuration Test | Successful |
| UFW Firewall | Active |
| SSH After Firewall Activation | Successful |
| Website After Firewall Activation | Successful |

## 8. Skills Demonstrated

- Linux Server Administration
- Virtual Machine Deployment
- Basic TCP/IP Networking
- Network Troubleshooting
- SSH Remote Administration
- Nginx Web Server Management
- Static Website Deployment
- Firewall Configuration with UFW
- Package Management & Troubleshooting
- Basic Infrastructure Testing

## 9. Project Evidence

Screenshots and implementation evidence are documented separately in the project repository.

Evidence categories:
- Virtual machine configuration.
- Ubuntu Server installation.
- Server hostname verification.
- Network configuration and connectivity testing.
- DPKG troubleshooting.
- OpenSSH installation and remote access.
- Nginx installation and service status.
- Website deployment and browser testing.
- HTTP response and Nginx configuration validation.
- UFW configuration and post-firewall testing.

## 10. Conclusion & Future Improvements

The Ubuntu Server deployment project was successfully completed.

The server was installed and configured using VirtualBox, established network connectivity with the Windows host, enabled remote administration through OpenSSH, and hosted a static website using Nginx.

UFW was also configured to restrict SSH and HTTP access to the local network subnet. Final testing confirmed that both services remained operational after firewall activation.

### Future Improvements

Potential improvements for the next stage include:

- Implement HTTPS using SSL/TLS.
- Configure SSH key-based authentication.
- Implement automated server backup and recovery.
- Monitor server resources and system logs.
- Perform Linux server security hardening.
- Implement centralized security monitoring using Wazuh.

---

**Project Status:** Completed

**Environment:** VirtualBox | Ubuntu Server 22.04.2 LTS

*This project is part of my continuous learning journey in IT Support, Linux Administration, and IT Infrastructure.*
