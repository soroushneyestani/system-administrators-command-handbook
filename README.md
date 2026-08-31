# System Administrator's Command Handbook

**Windows · PowerShell · Linux · macOS**

> One task. Three operating systems. One command reference.

A practical, cross-platform command-line reference for system administrators.

**Public release: Coming Soon**

---

## About the Project

**System Administrator's Command Handbook** is a task-oriented reference for administrators working across Windows, PowerShell, Linux, and macOS.

The project originally began in **2012** and reached its original completed edition in **2014**.

In **2026**, the project was reopened and completely reconstructed for modern system administration.

The 2026 edition is **not a reprint of the 2014 handbook**.  
It is a re-engineering of the original concept, with a modern technical baseline, expanded platform coverage, updated administration tools, cross-platform comparisons, lifecycle information, operational guidance, and safety considerations.

---

## Project Timeline

**2012 — Initial Version**  
The first version of the command-reference project was created.

**2014 — Original Final Edition**  
The original handbook reached its completed form based on the system-administration landscape of that period.

**2026 — Complete Reconstruction**  
The project was redesigned and technically rebuilt for modern Windows, PowerShell, Linux, and macOS administration.

---

## Core Idea

Traditional command references often begin with a command name.

This handbook begins with the **administrative task**.

The goal is to help answer questions such as:

- Which tool should I use for this task?
- What is the equivalent on another operating system?
- Is this command still current?
- Does it require administrative privileges?
- Is the operation potentially destructive?
- What should be checked before using it in production?

Where appropriate, the handbook compares equivalent administrative concepts across:

| Platform | Coverage |
| --- | --- |
| Windows | CMD, native administration tools, Windows Server utilities |
| PowerShell | Administration, objects, pipelines, remoting and automation |
| Linux | Bash, GNU/Linux tools, systemd, networking, storage and security |
| macOS | zsh and native administration tools |

---

## Major Coverage Areas

- Shell Fundamentals & Automation
- Files, Directories, Text & Data
- Users, Groups, Permissions & Identity
- Processes, Services & Sessions
- Storage, Filesystems & Backup
- Networking, DNS & Remote Administration
- Software, Packages, Updates & Deployment
- Logs, Performance, Inventory & Diagnostics
- Security, PKI, Encryption & Access Control
- Scheduling & Automation
- Active Directory & Enterprise Administration
- Native macOS Administration

---

## More Than Syntax

Depending on the tool, handbook entries may include:

- Purpose and administrative context
- Syntax
- Practical administrator examples
- Privilege requirements
- Operational guidance
- Safety considerations
- Version and platform notes
- Cross-platform equivalents
- Authoritative references
- Tool lifecycle status

### Lifecycle Status

The handbook distinguishes between tools that merely still exist and tools that should actually be selected for modern administration.

Entries may therefore be identified as:

**Current · Legacy · Deprecated · Removed**

---

## Cross-Platform by Design

A system administrator may work with Windows endpoints, Linux servers, macOS workstations, PowerShell automation, SSH sessions, and enterprise infrastructure during the same working day.

The handbook treats these platforms as different implementations of many shared administrative concepts rather than completely isolated environments.

For example:

| Administrative Task | Windows | PowerShell | Linux | macOS |
| --- | --- | --- | --- | --- |
| List processes | `tasklist` | `Get-Process` | `ps` | `ps` |
| Manage services | `sc` | `Get-Service` | `systemctl` | `launchctl` |
| Inspect network configuration | `ipconfig` | `Get-NetIPConfiguration` | `ip` | `networksetup` |
| Manage disks | `diskpart` | Storage cmdlets | `lsblk` / `parted` | `diskutil` |

---

## Editions

The reconstructed handbook is being prepared in three language editions:

### English
**System Administrator's Command Handbook**

### Deutsch
**Das Kommandozeilen-Handbuch für Systemadministratoren**

### فارسی
**راهنمای جامع دستورات برای مدیران سیستم**

All three editions follow the same underlying technical architecture.

---

## Publication Status

| Edition | Status |
| --- | --- |
| English | Coming Soon |
| Deutsch | Coming Soon |
| فارسی | Coming Soon |

---

## About This Repository

This repository is the **official public companion repository** for the handbook.

It will provide resources such as:

- Cross-platform quick references
- Selected examples
- Technical updates
- Errata and corrections
- Version notes
- Supporting administration resources

The complete publication manuscript and print-production files are **not distributed through this repository**.

---

## Planned Companion Resources

The repository will gradually include references for areas such as:

- Services
- Networking
- Storage
- Processes
- Users and permissions
- Logs and diagnostics
- Security

These resources are intended to complement the handbook and provide a continuously maintainable technical layer for information that may change after publication.

---

## Errata & Technical Updates

Operating systems evolve.

Commands may be deprecated, replaced, removed, or change behavior after a printed edition has been released.

Verified corrections and important platform changes will therefore be documented in this repository.

---

## Website

The official project page will be published with additional information about the handbook, its history, language editions, companion resources, and future availability.

**Website: Coming Soon**

---

## Author

**Soroush Neyestani**

---

## Release

**Public release: Coming Soon**

English · Deutsch · فارسی

---

**One task. Three operating systems. One command reference.**
