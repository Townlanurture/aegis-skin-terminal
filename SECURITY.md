# Security Policy

## Supported versions

| Version | Supported | Notes |
| --- | --- | --- |
| 1.12 | ✅ | Current release line |
| < 1.12 | ⛔ | Pre-release development builds |

Bug fixes land on the current line only. Hotfixes for a critical issue are
backported if the fix is isolated to the spread engine.

## Scope

Aegis Skin Terminal is a local-first desktop app. In scope:

- Anything that reads or writes state under the app-data directory
- The TOTP derivation path and how shared secrets are held in memory
- Request handling in the venue adapters and quote polling
- CSV export and any path handling around it

Out of scope: the venues themselves, Steam account security, phishing reports
and anything reproducible only with a modified local build.

## Reporting a vulnerability

1. Open a **private security advisory** on this repository (Security tab →
   Report a vulnerability). This is the fastest path.
2. If the advisory form is unavailable, open a regular issue titled
   `security: <one-line summary>` with reproduction steps and nothing else —
   details go into the private thread once it exists.

## What to include

- Affected build (see the About sidebar or `package.json`)
- Minimal reproduction or a short screen recording
- Whether the app held a vault imported at the time
- Your assessment of impact, if you have one

## Response expectations

| Stage | Target |
| --- | --- |
| First response | 72 hours |
| Triage and severity call | 7 days |
| Fix or mitigation on a release | depends on severity, critical within 14 days |

Reports are answered in the order they arrive. Duplicate reports of the same
issue are merged and credited together on request.

## Handling of vault data

Vaults never leave the machine. A report that involves a leaked shared secret
should treat that secret as compromised regardless of the fix — rotate it with
the venue, not only in the app.

## Credits

Responsible reporters are listed in the release notes of the first fixed
build, by name or handle, whichever they prefer.
