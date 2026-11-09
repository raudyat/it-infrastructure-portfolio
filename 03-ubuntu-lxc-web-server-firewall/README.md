# Ubuntu LXC Web Server & Firewall

## Project Overview

This project documents my hands-on practice in deploying and managing a web server using Ubuntu 24.04 LTS inside a Proxmox LXC container.

The project focuses on Linux system administration, remote SSH access, Nginx web server deployment, firewall configuration, and HTTP service validation.

## Environment

| Component | Details |
|---|---|
| Virtualization Platform | Proxmox VE |
| Container | Ubuntu 24.04 LTS LXC |
| Web Server | Nginx |
| Firewall | UFW |
| Web Technologies | HTML & CSS |
| Client OS | Windows |

## Practical Activities

### 1. Linux User Administration
- Created a dedicated administrator account (`adminlab`).
- Added the account to the sudo group.
- Verified user permissions.

### 2. SSH Remote Administration
- Configured and tested SSH access.
- Successfully connected from Windows using an SSH tunnel.
- Verified that root password login was restricted.
- Performed administration using a non-root account.

### 3. Nginx Web Server Deployment
- Installed Nginx on Ubuntu LXC.
- Enabled and started the Nginx service.
- Verified service status using systemctl.
- Tested the default Nginx web page.

### 4. Website Development & Deployment
- Created a company website for PT Digital Nusantara.
- Developed the website using HTML and CSS.
- Added navigation, hero section, service cards, profile, and contact sections.
- Deployed the website to the Nginx web root directory.

### 5. Firewall Configuration
- Configured UFW firewall.
- Applied default deny incoming and allow outgoing policies.
- Allowed SSH traffic (TCP port 22).
- Allowed HTTP traffic (TCP port 80).
- Activated and verified firewall rules.

### 6. Service & HTTP Validation
- Verified Nginx service status.
- Tested HTTP response using `curl`.
- Obtained `HTTP/1.1 200 OK`.
- Successfully accessed the website from a Windows browser through an SSH tunnel.

## Skills Demonstrated

- Linux User and Permission Management
- SSH Remote Administration
- Ubuntu Server Administration
- Nginx Installation and Configuration
- HTML & CSS Website Deployment
- UFW Firewall Management
- HTTP Troubleshooting and Validation
- Basic Server Security

## Project Results

The Ubuntu LXC web server was successfully deployed and configured.

The Nginx service remained active, UFW firewall rules were applied, and the PT Digital Nusantara website was successfully displayed in a Windows browser through an SSH tunnel.

## Scope & Limitations

Browser access was performed through an SSH tunnel. Direct network access through Proxmox routing or port forwarding has not yet been implemented.

## Documentation

Detailed practical documentation, configuration evidence, terminal outputs, and screenshots are available in the PDF included in this repository.

## Future Improvements

- Configure direct HTTP access through network routing or port forwarding.
- Implement SSH hardening.
- Improve Nginx security configuration.
- Configure server backup and monitoring.
- Restrict SSH and HTTP access based on network requirements.

---

**Project Category:** System Administration & IT Infrastructure  
**Status:** Completed (with planned improvements)
