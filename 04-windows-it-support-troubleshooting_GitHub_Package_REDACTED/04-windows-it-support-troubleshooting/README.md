# Project 04 — Windows IT Support & Troubleshooting Lab

**Status:** In progress  
**Environment:** Windows Host + Oracle VirtualBox  
**Scenario:** Workstation support lab for PT Digital Nusantara

## Project objective

Build practical experience for an IT Support / Junior System Administrator role by deploying a Windows 11 workstation, verifying its configuration, inspecting devices and storage, and diagnosing network connectivity.

This repository records only tasks that have been performed and evidenced. Planned exercises are clearly marked as pending.

## Lab environment

| Item | Observed configuration |
|---|---|
| Virtualization platform | Oracle VirtualBox |
| Guest OS | Windows 11 Pro |
| Version / build | 26H2 / 26300.9711 |
| VM name | Windows 11 IT Support |
| Computer name | `PTDN-CLIENT01` |
| Local user | `itadmin` |
| VM memory | 4096 MB configured; approximately 3.98 GB reported in guest |
| Virtual CPUs | 2 |
| Virtual disk | 80 GB configured; 79.98 GB shown in Disk Management |
| Network | VirtualBox NAT, based on observed `10.0.2.15` address and `10.0.2.2` gateway |
| Guest Additions | Oracle VM VirtualBox Guest Additions 7.0.18 |

## Portfolio sections

| Section | Contents | Status |
|---|---|---|
| [01 — Installation](01-installation/README.md) | ISO, VM creation, Windows Setup, disk selection, OOBE, local account | Completed |
| [02 — Initial Configuration](02-initial-configuration/README.md) | Desktop, hostname, user, Windows version | Completed |
| [03 — Guest Additions](03-guest-additions/README.md) | Guest Additions installation and clipboard test | Completed |
| [04 — System & Hardware Verification](04-system-hardware-verification/README.md) | `systeminfo`, CPU, RAM, virtual disk inspection | Completed |
| [05 — Device Manager & Driver Checks](05-device-manager-driver-checks/README.md) | Device inventory and network/display adapter status | Completed for checked devices |
| [06 — Storage Management](06-storage-management/README.md) | Disk Management, EFI, C:, Recovery, optical media | Completed |
| [07 — Network Troubleshooting](07-network-troubleshooting/README.md) | IP configuration, ping, DNS resolution | Basic checks passed; DNS discrepancy investigation pending |

## Key results

- Windows 11 Pro installed and reached the desktop.
- Local account `itadmin` and computer name `PTDN-CLIENT01` verified.
- Guest Additions 7.0.18 installed; resolution adjustment and bidirectional clipboard test succeeded.
- Windows reported 2 virtual processors and approximately 3.98 GB memory.
- Network and display adapter properties both reported: `This device is working properly.`
- Disk 0 appeared Online at approximately 79.98 GB; EFI, Windows, and Recovery partitions were shown as Healthy.
- Gateway ping: 3 replies received, 0% loss.
- Public IP ping to `8.8.8.8`: 4 replies received, 0% loss; average approximately 22 ms.
- `nslookup google.com` succeeded.

## Important notes

- `systeminfo` reported Windows 11 Pro, Version 26H2, OS Build 26300.9711. Keep this as the observed lab build, not a claim that it is a production release recommendation.
- The guest OS reported processor identity `Intel Core i7-10870H`; this is the processor identity exposed by the hypervisor. The VM was configured with 2 vCPUs.
- Disk Management showed the C: volume as BitLocker Encrypted. Do not alter partitions or attempt recovery without ensuring the recovery key is safely available.
- The DNS server initially appeared as `192.168.1.1` in one capture, then later appeared as `192.168.100.1` in both `ipconfig /all` and `Get-DnsClientServerAddress`. The reason for the earlier difference has not been established. No manual DNS changes have been made.
- The DNS failure simulation and recovery exercise has **not** been performed yet.

## Repository evidence

Each section contains its own README and screenshots folder. Screenshot filenames describe the evidence captured. Review screenshots before public upload and remove any sensitive information that is not needed for the portfolio.

## Next planned work

1. Investigate the DNS-server discrepancy while preserving the current working configuration.
2. Record the current DNS configuration.
3. Run a controlled DNS failure simulation inside the VM only.
4. Demonstrate that IP connectivity can remain available while DNS resolution fails.
5. Restore the original DHCP-provided DNS configuration and verify resolution.
6. Continue with Windows services, Event Viewer, user management, and further support scenarios.
