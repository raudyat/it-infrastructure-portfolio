# 04 — System & Hardware Verification

## Objective
Use Windows tools and PowerShell to inventory the operating system and virtual hardware.

## Commands used
```powershell
systeminfo

Get-CimInstance Win32_Processor |
Select-Object Name, NumberOfCores, NumberOfLogicalProcessors

Get-CimInstance Win32_ComputerSystem |
Select-Object Manufacturer, Model,
@{Name="RAM_GB";Expression={[math]::Round($_.TotalPhysicalMemory/1GB,2)}}

Get-PhysicalDisk |
Select-Object FriendlyName, MediaType, Size, HealthStatus
```

## Observed results
| Item | Result |
|---|---|
| OS | Windows 11 Pro, build 26300.9711 |
| System manufacturer/model | innotek GmbH / VirtualBox |
| System type | x64-based PC |
| Processor exposed to guest | Intel Core i7-10870H @ 2.20 GHz |
| Virtual CPU allocation | 2 cores / 2 logical processors |
| Guest-visible RAM | Approximately 3.98 GB |
| Virtual disk | VBOX HARDDISK, HealthStatus Healthy |

The processor name is the identity exposed by the hypervisor; it does not mean the VM has access to all physical host cores.

## Outcome
The guest OS recognized its assigned virtual resources. Evidence is in `screenshots/`.
