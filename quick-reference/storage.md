# Storage & Filesystems — Cross-Platform Quick Reference

| Task | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| List disks | `diskpart` → `list disk` | `Get-Disk` | `lsblk` | `diskutil list` |
| Volumes | `mountvol` | `Get-Volume` | `findmnt` | `diskutil list` |
| Usage | native tools | `Get-Volume` | `df -h` | `df -h` |
| Mount | `mountvol` | Storage cmdlets | `mount` | `diskutil mount` |

Treat partitioning, formatting, filesystem creation/repair, RAID/LVM changes, wiping, and encryption as high-risk operations.
