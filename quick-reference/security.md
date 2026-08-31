# Security & Access Control — Cross-Platform Quick Reference

| Area | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| Firewall | Windows firewall tooling | Firewall cmdlets | `nft`, `firewall-cmd`, `ufw` | `pfctl` |
| Disk encryption | BitLocker tools | BitLocker cmdlets | LUKS tooling | `fdesetup` |
| Certificates | `certutil`, `certreq` | PKI/certificate tooling | `openssl` | `security` |
| File permissions | `icacls` | ACL tooling | `chmod`, `setfacl` | `chmod`, ACLs |

A command that succeeds is not automatically a secure configuration. Verify scope, trust boundaries, auditability, and rollback.
