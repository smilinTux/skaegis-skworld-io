# Security Policy

This repo is a static marketing site with no runtime, no forms, no backend and no secrets. It is **not a crypto component** (maturity T0) and states no cryptographic claims.

## Threat model summary
- **In scope:** content integrity of the published site (tampered HTML or CSS, injected third-party scripts), the `CNAME` and Pages configuration (domain takeover), and any claim on the page that misstates what the product does.
- **Out of scope:** the skAegis product itself, which has its own policy when released.

## Reporting a vulnerability
Open a private security advisory on this GitHub repository (Security tab, "Report a vulnerability"). Please do not file public issues for security reports. We aim to acknowledge within 5 business days. Overclaims or misleading security statements on the site are treated as reportable issues, per the SK security-disclosure standard.

## Secret handling
No secrets belong in this repo. Never commit credentials, tokens or internal host details.

## Dependency posture
No runtime dependencies, no package manager, no third-party scripts or fonts. Keep it that way. Branch protection on `main` is the main control.
