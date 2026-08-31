# Service Management — Cross-Platform Quick Reference

| Task | Windows | PowerShell | Linux / systemd | macOS / launchd |
| --- | --- | --- | --- | --- |
| Inspect | `sc.exe query` | `Get-Service` | `systemctl status <unit>` | `launchctl print <target>` |
| Start | `sc.exe start <service>` | `Start-Service` | `systemctl start` | `launchctl kickstart` |
| Stop | `sc.exe stop <service>` | `Stop-Service` | `systemctl stop` | `launchctl bootout` |
| Restart | Stop + Start | `Restart-Service` | `systemctl restart` | `launchctl kickstart -k` |

Before changing production services, verify the exact target, dependencies, workload impact, logs, and recovery path.
