# 06 — Storage Management

## Objective
Inspect the Windows disk and partition layout using Disk Management.

## Tool
Run:
```text
diskmgmt.msc
```

## Observed layout
| Disk / volume | Approximate size | Observed status |
|---|---:|---|
| Disk 0 | 79.98 GB | Basic, Online |
| EFI System Partition | 200 MB | Healthy |
| Windows (C:) | 78.91 GB | Healthy |
| Recovery Partition | 900 MB | Healthy |
| Guest Additions CD (D:) | 50 MB | Healthy optical media |

C: showed approximately 44.10 GB free (56%). Disk Management displayed `BitLocker Encrypted` for C:.

## Safety note
No partitions were deleted, formatted, resized, or otherwise modified. Before any future BitLocker recovery or partition operation, ensure the recovery key is available and safely stored.

## Outcome
The virtual disk and expected Windows partitions were visible and reported Healthy. Evidence is in `screenshots/`.
