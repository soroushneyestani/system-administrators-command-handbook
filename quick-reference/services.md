# Service Management — Cross-Platform Quick Reference

> Windows · PowerShell · Linux · macOS

This quick reference compares common service-management tasks across the four administration environments covered by the **System Administrator's Command Handbook**.

The commands below are intended as a fast operational map rather than a replacement for platform-specific documentation.

---

## Quick Comparison

| Task | Windows | PowerShell | Linux / systemd | macOS / launchd |
| --- | --- | --- | --- | --- |
| List / inspect services | `sc.exe query` | `Get-Service` | `systemctl list-units --type=service` | `launchctl list` |
| Inspect one service | `sc.exe query <service>` | `Get-Service -Name <service>` | `systemctl status <unit>` | `launchctl print <service-target>` |
| Start | `sc.exe start <service>` | `Start-Service -Name <service>` | `sudo systemctl start <unit>` | `launchctl kickstart <service-target>` |
| Stop | `sc.exe stop <service>` | `Stop-Service -Name <service>` | `sudo systemctl stop <unit>` | `launchctl bootout <service-target>`* |
| Restart | Stop + Start | `Restart-Service -Name <service>` | `sudo systemctl restart <unit>` | `launchctl kickstart -k <service-target>` |
| Enable at startup | `sc.exe config <service> start= auto` | `Set-Service` | `sudo systemctl enable <unit>` | Defined through launchd configuration / domain state |
| Disable | `sc.exe config <service> start= disabled` | `Set-Service` | `sudo systemctl disable <unit>` | `launchctl disable <service-target>` |

\* `bootout` removes a service from a launchd domain. macOS service management does not map one-to-one to the Windows or systemd service model.

---

# Windows — Service Control

Windows provides the native Service Control utility:

```text
sc.exe
````

## Inspect a Service

```cmd
sc.exe query Spooler
```

## List Services

```cmd
sc.exe query type= service state= all
```

## Start a Service

```cmd
sc.exe start Spooler
```

## Stop a Service

```cmd
sc.exe stop Spooler
```

## Configure Automatic Startup

```cmd
sc.exe config Spooler start= auto
```

## Configure Manual Startup

```cmd
sc.exe config Spooler start= demand
```

## Disable a Service

```cmd
sc.exe config Spooler start= disabled
```

> Note: `sc.exe` syntax requires attention to spacing around configuration parameters such as `start=`.

---

# PowerShell — Service Management

PowerShell exposes Windows services as objects.

## List Services

```powershell
Get-Service
```

## Inspect One Service

```powershell
Get-Service -Name Spooler
```

## Find Running Services

```powershell
Get-Service | Where-Object Status -eq 'Running'
```

## Start a Service

```powershell
Start-Service -Name Spooler
```

## Stop a Service

```powershell
Stop-Service -Name Spooler
```

## Restart a Service

```powershell
Restart-Service -Name Spooler
```

## Inspect Dependencies

```powershell
Get-Service -Name Spooler -RequiredServices
```

```powershell
Get-Service -Name Spooler -DependentServices
```

### Operational Note

Before stopping an important service, inspect its dependencies and determine whether other services or users rely on it.

For changes that affect production workloads, verify the exact service name and expected recovery path first.

---

# Linux — systemd

On systemd-based Linux systems, `systemctl` is the primary interface for inspecting and controlling services and other systemd units.

## List Active Service Units

```bash
systemctl list-units --type=service
```

## List Installed Service Unit Files

```bash
systemctl list-unit-files --type=service
```

## Inspect a Service

```bash
systemctl status sshd.service
```

Depending on the distribution, the service may use another unit name, for example:

```bash
systemctl status ssh.service
```

## Start

```bash
sudo systemctl start sshd.service
```

## Stop

```bash
sudo systemctl stop sshd.service
```

## Restart

```bash
sudo systemctl restart sshd.service
```

## Reload Service Configuration

```bash
sudo systemctl reload sshd.service
```

## Enable at Boot

```bash
sudo systemctl enable sshd.service
```

## Disable at Boot

```bash
sudo systemctl disable sshd.service
```

## Check Whether It Is Enabled

```bash
systemctl is-enabled sshd.service
```

## Check Whether It Is Active

```bash
systemctl is-active sshd.service
```

### Important Distinction

These are not equivalent:

```bash
systemctl reload example.service
```

and:

```bash
systemctl daemon-reload
```

`reload` asks the service itself to reload its configuration.

`daemon-reload` tells systemd to reload unit-file definitions after unit files or related systemd configuration have changed.

### Operational Note

Before restarting or stopping a production service:

1. Verify the exact unit.
2. Inspect its current status.
3. Check dependencies and triggering units when relevant.
4. Review recent logs if the service is unhealthy.
5. Confirm the effect on active workloads.

---

# macOS — launchd / launchctl

macOS uses `launchd` to manage system daemons and per-user agents.

Its model differs from both Windows Services and systemd.

Modern `launchctl` administration uses concepts such as:

* domains
* service targets
* bootstrap
* bootout
* enable / disable
* kickstart

---

## List Loaded Jobs

```bash
launchctl list
```

## Inspect launchd State

A service is addressed through a launchd domain and service identifier.

Conceptually:

```text
domain/service.identifier
```

Examples of domains include:

```text
system
user/<uid>
gui/<uid>
```

## Start / Kick a Loaded Service

```bash
launchctl kickstart <service-target>
```

## Restart a Loaded Service

```bash
launchctl kickstart -k <service-target>
```

The `-k` option terminates the existing instance before starting it again.

## Bootstrap a Service

```bash
launchctl bootstrap <domain-target> <service-path>
```

## Remove a Service from a Domain

```bash
launchctl bootout <domain-target> <service-path>
```

or, where appropriate:

```bash
launchctl bootout <service-target>
```

## Disable a Service

```bash
launchctl disable <service-target>
```

## Enable a Service

```bash
launchctl enable <service-target>
```

### Legacy Commands

Older documentation and scripts may contain:

```bash
launchctl load
launchctl unload
```

These belong to the legacy `launchctl` interface.

For current administration, prefer the modern domain-oriented commands such as:

```text
bootstrap
bootout
enable
disable
kickstart
```

where appropriate.

### Operational Note

Do not assume that a launchd job behaves exactly like a Windows Service or systemd service.

Before modifying it, identify:

* its domain,
* service identifier,
* plist location,
* whether it is a LaunchAgent or LaunchDaemon,
* and whether the configuration is system-wide or user-specific.

---

# Conceptual Mapping

The four platforms implement similar administrative objectives through different service-management models.

```text
Administrative Task
        │
        ├── Windows
        │      └── Service Control Manager
        │             └── sc.exe
        │
        ├── PowerShell
        │      └── ServiceController objects
        │             └── Get-Service / Start-Service / ...
        │
        ├── Linux
        │      └── systemd
        │             └── systemctl
        │
        └── macOS
               └── launchd
                      └── launchctl
```

The important lesson is therefore not:

> "These commands are identical."

It is:

> "These tools solve comparable administrative problems using different platform models."

---

# Safety

Service operations can interrupt:

* network connectivity,
* remote sessions,
* authentication,
* databases,
* application workloads,
* scheduled processing,
* storage access,
* monitoring,
* security controls.

Before stopping or restarting a production service:

* Identify the exact target.
* Inspect its current state.
* Check dependencies.
* Determine who or what is using it.
* Review relevant logs.
* Confirm that recovery or rollback is possible.
* Prefer graceful service control over terminating the underlying process directly.

---

# Handbook

This quick reference is a companion to:

**System Administrator's Command Handbook**

**Windows · PowerShell · Linux · macOS**

The complete handbook provides additional syntax, administrator examples, privilege information, operational guidance, lifecycle status, safety notes, and cross-platform references.

**English · Deutsch · فارسی**

**Public release: Coming Soon**

---

## Technical Reference Basis

This quick reference is based on current platform documentation, including:

* Microsoft Windows command documentation
* Microsoft PowerShell documentation
* systemd / `systemctl` documentation
* macOS `launchctl` documentation

Platform behavior may change after publication. Always verify production-sensitive operations against the documentation and local help available on the target system.

````
