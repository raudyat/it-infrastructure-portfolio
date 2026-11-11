# 02 — Initial Windows Configuration

## Objective
Verify the Windows workstation identity and operating-system version after installation.

## Configuration
- Computer name: `PTDN-CLIENT01`
- Local account: `itadmin`
- OS: Windows 11 Pro
- Version: 26H2
- OS build: 26300.9711
- Architecture: x64

## Verification commands
```powershell
hostname
whoami
winver
```

## Observed results
- `hostname` returned `PTDN-CLIENT01`.
- `whoami` returned `ptdn-client01\itadmin`.
- `winver` displayed Windows 11 Pro, Version 26H2, OS Build 26300.9711.

## Outcome
The workstation name, local user, and Windows version were verified. Screenshots are in `screenshots/`.
