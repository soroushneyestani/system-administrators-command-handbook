# Logs & Diagnostics — Cross-Platform Quick Reference

| Task | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| Logs | `wevtutil` | `Get-WinEvent` | `journalctl` | `log show` |
| Follow | event tooling | event workflows | `journalctl -f` | `log stream` |
| System info | `systeminfo` / `msinfo32` | `Get-ComputerInfo` | `uname`, `lscpu` | `system_profiler`, `sw_vers` |
| Performance | `typeperf`, `perfmon` | `Get-Counter` | `vmstat`, `iostat`, `sar` | `vm_stat`, `iostat` |

Correlate logs with process state, sockets, resources, service state, and recent changes.
