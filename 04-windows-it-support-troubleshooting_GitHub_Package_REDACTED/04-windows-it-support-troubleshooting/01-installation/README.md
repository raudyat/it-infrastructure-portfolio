# 01 — Windows 11 Installation

## Objective
Deploy a Windows 11 Pro workstation in VirtualBox for the PT Digital Nusantara IT Support lab.

## Work performed
1. Opened Microsoft's Windows 11 download page and selected the x64 ISO option.
2. Created a VirtualBox VM named `Windows 11 IT Support`.
3. Configured the VM with 4096 MB RAM, 2 virtual CPUs, EFI enabled, and an 80 GB virtual disk.
4. Attached the Windows 11 ISO to the virtual optical drive.
5. Resolved the initial boot attempt by checking the ISO attachment and booting from the installation media.
6. Selected Install Windows 11 and installed to the 80 GB unallocated virtual disk.
7. Completed OOBE, named the device `PTDN-CLIENT01`, selected personal-use setup, and created a local account named `itadmin`.
8. Completed Windows privacy setup and reached the desktop.

## Evidence
Screenshots are stored in this section's `screenshots/` folder in chronological order.

## Notes
- The temporary black screen occurred during initial OOBE. The setup later proceeded to Microsoft account configuration and the Windows desktop.
- The Windows installation was performed inside the VM. The host laptop's operating system and physical disk were not the installation target.
- The virtual disk was selected as the destination; no host disk partitions were modified.

## Outcome
Windows 11 Pro successfully reached the desktop. Further configuration and verification are documented in the following sections.
