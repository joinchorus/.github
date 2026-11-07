# Security Policy

## Official Domains & Ecosystem

Chorus operates strictly across standardized public subdomains:
- **Public Site:** [joinchorus.app](https://joinchorus.app)
- **Application & API:** [chat.joinchorus.app](https://chat.joinchorus.app)
- **Documentation:** [docs.joinchorus.app](https://docs.joinchorus.app)

---

## Reporting Vulnerabilities

We take the security and anonymity guarantees of Chorus seriously. If you discover a security vulnerability, privacy defect, or potential data leak, please report it to us confidentially before publishing it publicly.

### How to Report

1. **GitHub Private Vulnerability Reporting** (preferred): open a confidential report from the **Security** tab of the affected repository, e.g. [joinchorus/chorus](https://github.com/joinchorus/chorus/security/advisories/new). It is enabled on every joinchorus repository.
2. **Email**: Send detailed disclosures to `security@joinchorus.app` (or maintainers at `barissalih@babacan.me` / `baris.salih.babacan@gmail.com`).

Please include:
- A description of the vulnerability and its potential impact.
- Step-by-step reproduction instructions or a minimal proof-of-concept.
- Any proposed mitigations or remediation patches.

### Responsible Disclosure & Timeline

- We acknowledge vulnerability reports within 48 hours.
- We provide periodic status updates during triage and fix implementation.
- We request that you do not publicly disclose exploitable vulnerabilities until an official patch has been released and deployed.

---

## Security Scope & Core Guarantees

We are particularly interested in reports related to:
- **Anonymity Breaches**: Vulnerabilities that allow cross-thread correlation or unmasking of ephemeral identities.
- **IP Address Leaks**: Exposure of client IP addresses beyond the server layer.
- **Data Integrity & Tampering**: Exploits that rewrite or bypass the append-only Git commit history or the moderation records.
- **Authorization Bypasses**: Bypassing admin authentication on `/api/v0.1/moderation/*` or `/api/v1/moderation/*`.
- **Injection & Memory Safety**: Injection vulnerabilities in Go backend, React SPA XSS, or memory safety issues.
