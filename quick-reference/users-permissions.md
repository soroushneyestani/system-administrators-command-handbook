# Users & Permissions — Cross-Platform Quick Reference

| Task | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| Current user | `whoami` | identity/environment APIs | `whoami` / `id` | `whoami` / `id` |
| Local users | `net user` | `Get-LocalUser` | account tools | `dscl . list /Users` |
| Groups | `net localgroup` | `Get-LocalGroup` | `groups` | `dseditgroup` |
| File permissions | `icacls` | ACL tooling | `chmod`, `chown`, `setfacl` | `chmod`, `chown` |

Before recursive permission changes, confirm the exact path and inheritance/ACL behavior.
