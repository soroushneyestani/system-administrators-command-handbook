# Processes & Diagnostics — Cross-Platform Quick Reference

| Task | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| List | `tasklist` | `Get-Process` | `ps aux` | `ps aux` |
| Find | `tasklist /FI` | `Get-Process -Name` | `pgrep` | `pgrep` |
| Stop | `taskkill` | `Stop-Process` | `kill` / `pkill` | `kill` / `pkill` |
| Monitor | `perfmon` | `Get-Counter` | `top`, `vmstat`, `free` | `top`, `vm_stat` |

Prefer graceful application/service control over forceful termination when possible.
