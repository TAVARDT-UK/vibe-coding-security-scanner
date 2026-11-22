# Vibe Coding Security Scanner & AI-Generated App Auditor | TAVARDT UK

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Vibe Coding Security](https://img.shields.io/badge/Vibe%20Coding-Security%20Hardened-00d26a.svg)](README.md)
[![Language](https://img.shields.io/badge/Language-English%20(UK)-green.svg)](README.md)
[![Engineering](https://img.shields.io/badge/TAVARDT-Cybersecurity-5b3cf5.svg)](https://ag.tavardt.com/uk/cybersecurity/)

Open-source security scanner auditing live applications built with vibe coding tools (Cursor, Lovable, Bolt, v0). Detects leaked frontend API keys, Supabase RLS gaps, exposed sourcemaps, and sensitive files.

## Interactive Web Application

Access the live online tool and evaluate in real-time:

- [https://tavardt-uk.github.io/vibe-coding-security-scanner/](https://tavardt-uk.github.io/vibe-coding-security-scanner/)

---

## 1. Vibe Coding Security Scanner Overview

AI-assisted engineering and *vibe coding* allows teams to deploy working applications rapidly using **Cursor, Lovable.dev, Bolt.new, v0, and Replit**.

However, rapid deployment without architectural security checks routinely exposes production secrets, unshielded database endpoints, and private source code directly to client browsers.

This repository provides an automated Python scanner that inspects **the public perimeter of any deployed web application**, identifying critical risks before exploitation.

---

## 2. Audited Vulnerabilities & Threat Vectors

| Risk Vector | Root Cause in Vibe Coding | Technical Impact |
| :--- | :--- | :--- |
| **Frontend API Key Leaks** | Private OpenAI (`sk-...`), Stripe, or cloud keys placed in client-facing `.env` variables. | Visitors extract credentials from DevTools, draining commercial API quotas. |
| **Unprotected Supabase RLS** | Databases provisioned without active Row Level Security (RLS) policies. | The public `anon_key` allows unauthorized users to exfiltrate or delete records via REST. |
| **Exposed Production Sourcemaps** | Build tools configured to output `.js.map` files directly to production domains. | Complete proprietary TypeScript/JavaScript source code is readable by anyone. |
| **Sensitive File Exposure** | Web hosting exposing `/.env` or `/.git/HEAD` files to public HTTP requests. | Full disclosure of environment secrets and version control trees. |
| **Missing Security Headers** | Omission of CSP, HSTS, and X-Frame-Options headers. | Increased exposure to Clickjacking, cross-site scripting (XSS), and transport tampering. |

---

## 3. Installation & Implementation Guide

### Quick Installation

```bash
git clone https://github.com/TAVARDT-UK/vibe-coding-security-scanner.git
cd vibe-coding-security-scanner
```

### Scan a Live Application URL

```bash
python scanner.py https://your-app.vercel.app
```

### Execution Options

```bash
# Output structured JSON audit report
python scanner.py https://your-app.vercel.app --json

# Disable sourcemap verification
python scanner.py https://your-app.vercel.app --no-sourcemaps
```

---

## 4. Perimeter Hardening & Engineering Support

If your audit surfaced exposed credentials, unprotected database tables, or requires professional edge security engineering:

* **Corporate Portal:** [TAVARDT UK](https://ag.tavardt.com/uk/cybersecurity/)
* **Direct Engineering Engagement:** [Contact Engineering Team](https://ag.tavardt.com/uk/contact/)

---

## Licence

Distributed under the open-source MIT Licence. Refer to the [`LICENSE`](LICENSE) file for complete details.  
Copyright (c) 2026 TAVARDT UK.
