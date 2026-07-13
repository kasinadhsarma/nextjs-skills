# Security Policy

## Scope

This repository contains **documentation and reference material** about Next.js architecture and deployment practices. It does not ship executable code, a backend service, or a published package.

Security concerns in scope:

- **Incorrect security guidance** — a recommendation in the docs that would make a Next.js app *less* secure if followed (e.g., missing server-side authorization example in the Server Action guide, an insecure middleware auth pattern)
- **Outdated security advice** — guidance that was correct at time of writing but has since been superseded by a known vulnerability, deprecation, or better practice
- **Dependency vulnerabilities** — if a code example recommends a package with a known CVE

Security concerns **out of scope** (this repo has no attack surface for):

- Infrastructure attacks (no servers, no databases, no auth)
- Supply chain attacks against this repo itself (no published package)
- Spam, phishing, or social engineering disclosures

---

## Supported Versions

Documentation is maintained against the latest stable Next.js release, with explicit notes where behavior differs from the prior major version.

| Next.js Version | Docs Status |
|---|---|
| 15.x (latest stable) | Actively maintained |
| 14.x | Referenced where caching/typing defaults differ |
| 13.x and earlier | Not supported |

---

## Reporting a Vulnerability

**Do not open a public GitHub issue for security-related reports.** Use one of the channels below.

### Option A — GitHub Private Vulnerability Reporting (preferred)

1. Go to the [Security tab](https://github.com/kasinadhsarma/nextjs-skills/security) of this repository
2. Click **"Report a vulnerability"**
3. Fill in the advisory form

This creates a private draft advisory visible only to maintainers.

### Option B — Email

Send a description to **kasinadhsarma@gmail.com** with the subject line:

```
[nextjs-skills] Security: <brief description>
```

Include:
- Which document and section contains the issue
- What the current guidance says
- Why it is incorrect or insecure
- What the correct guidance should be (if known)
- Any references (CVEs, OWASP advisories, official Next.js docs)

---

## Response Timeline

| Stage | Target |
|---|---|
| Acknowledgement | Within 48 hours |
| Initial assessment | Within 5 business days |
| Fix published | Within 14 days for high-severity; 30 days for others |
| Credit in changelog | Upon fix publication |

---

## Disclosure Policy

We follow **coordinated disclosure**:

1. Reporter submits privately
2. Maintainer confirms and assesses severity
3. Fix is prepared and reviewed
4. Fix is published and reporter is credited
5. A public disclosure summary is added to the repository changelog

We ask reporters to allow at least **14 days** before any public disclosure to give time for a fix to be prepared.

---

## Credits

We publicly credit reporters (by name or handle, at their preference) in the relevant commit message and changelog entry. Thank you for helping keep Next.js developers on the right path.
