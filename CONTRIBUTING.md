# Contributing

Thank you for your interest in improving the **System Administrator's Command Handbook** companion repository.

This repository is intended to support the handbook with verified technical corrections, platform updates, quick references, and selected examples.

The complete book manuscript is not maintained publicly in this repository.

---

## Ways to Contribute

Contributions are welcome in the following areas:

- Reporting technical errors
- Reporting outdated command behavior
- Reporting deprecated or removed tools
- Suggesting updated platform equivalents
- Reporting incorrect privilege requirements
- Suggesting authoritative documentation references
- Improving quick-reference material
- Reporting broken links
- Reporting technically significant translation issues
- Suggesting post-publication platform updates

---

## Before Opening an Issue

Before submitting a report, please check:

- `ERRATA.md`
- Existing GitHub Issues
- Relevant official documentation
- Whether the behavior is version-specific

A command behaving differently on another operating-system version does not always mean the handbook is incorrect.

Please include the exact environment whenever possible.

---

## Reporting a Technical Issue

Open a GitHub Issue and include as much of the following information as possible:

### Required Information

- Language edition
- Section or command name
- Operating system
- Operating-system version
- Description of the issue

### Recommended Information

- Page number, if applicable
- Shell or PowerShell version
- Exact command used
- Observed output or behavior
- Expected behavior
- Authoritative documentation reference
- Minimal reproducible example

---

## Example Issue

```text
Edition: English
Section: Networking
Entry: ip
Operating System: Ubuntu
Version: 26.xx

Issue:
The example uses an option that behaves differently on this version.

Observed behavior:
...

Expected behavior:
...

Reference:
Official documentation URL
````

---

## Authoritative Sources

Technical changes should be supported by authoritative documentation whenever possible.

Preferred sources include:

* Microsoft Learn
* Official PowerShell documentation
* Apple documentation
* Linux manual pages
* Upstream project documentation
* Distribution documentation
* Official vendor documentation

Community discussions, blogs, forum posts, and Q&A websites may help identify an issue, but should not normally be the sole basis for a technical correction.

---

## Pull Requests

Pull requests may be accepted for companion content such as:

* Quick-reference documents
* Selected examples
* Broken-link fixes
* Documentation improvements
* Clearly verified technical corrections

Please keep pull requests focused on one topic whenever possible.

Do not combine unrelated changes into a single pull request.

---

## Book Manuscript Changes

The complete publication manuscript is maintained separately.

Pull requests that attempt to reproduce, replace, or redistribute substantial portions of the book manuscript will not be accepted.

Verified corrections reported through this repository may be incorporated into:

* Online companion resources
* `ERRATA.md`
* Future print editions
* Future revised editions

---

## Translation Contributions

The handbook is prepared in:

* English
* Deutsch
* فارسی

Translation-related reports are welcome when they affect:

* Technical meaning
* Command interpretation
* Administrative terminology
* Safety guidance
* Platform behavior

Pure stylistic preferences may not result in a change.

---

## Security and Privacy

Do not include sensitive information in Issues or Pull Requests.

Never publish:

* Passwords
* API keys
* Access tokens
* Private keys
* Internal IP addresses unless necessary and anonymized
* Confidential hostnames
* Customer information
* Production credentials
* Proprietary company data

Sanitize command output before submitting it.

---

## Responsible Technical Examples

Some commands documented by this project can modify:

* Filesystems
* Permissions
* Services
* Users
* Network configuration
* Boot configuration
* Encryption
* Security policy
* Stored data

When contributing examples, prefer safe inspection commands where possible.

Destructive examples must clearly identify their risk and should not encourage execution without verification.

---

## Review Process

Submitted reports may go through the following process:

1. Initial review
2. Reproduction or documentation check
3. Verification against authoritative sources
4. Classification as:

   * Correction
   * Clarification
   * Version-specific behavior
   * Post-publication change
   * Not reproducible
5. Update of companion documentation or `ERRATA.md` when appropriate

Not every submitted issue will result in a change.

---

## Contribution Scope

The purpose of this repository is to maintain a reliable technical companion to the handbook.

The project is not intended to become:

* A general technical-support forum
* A troubleshooting service for individual systems
* A complete operating-system documentation mirror
* A replacement for official platform documentation

---

## Code Contributions

Reusable scripts or source-code examples may use a separate software license from the book and documentation.

The applicable license will be specified in the relevant directory or file.

---

## Questions

For general questions about the project, use the project website once available.

For technical corrections or repository-related issues, use GitHub Issues.

---

Thank you for helping keep the project accurate and useful.

````
