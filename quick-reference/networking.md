# Networking & DNS — Cross-Platform Quick Reference

| Task | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| IP configuration | `ipconfig /all` | `Get-NetIPConfiguration` | `ip addr` | `networksetup -getinfo <service>` |
| Routes | `route print` | `Get-NetRoute` | `ip route` | `netstat -rn` / `route` |
| DNS query | `nslookup` | `Resolve-DnsName` | `dig` | `dig` |
| TCP connections | `netstat -ano` | `Get-NetTCPConnection` | `ss -tulpn` | `netstat -anv` |

Troubleshoot in layers: interface → address → route → DNS → reachability → ports → application.
