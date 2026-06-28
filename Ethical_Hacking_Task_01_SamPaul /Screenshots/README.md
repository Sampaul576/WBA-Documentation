# Ethical Hacking Task 01 – Information Gathering & Reconnaissance

**Organization:** White Band Associates
**Task:** Passive Reconnaissance on a public target
**Status:** Documentation-only / passive recon (no exploitation performed)

## Folder structure to upload to GitHub

```
Ethical_Hacking_Task_01_YourName/
├── README.md                      (this file)
├── Reconnaissance_Report.pdf      (export the filled template as PDF)
├── Research_Notes.md
└── Screenshots/
    ├── 01_whois_lookup.png
    ├── 02_dns_enumeration.png
    ├── 03_tech_identification.png
    ├── 04_security_headers.png
    └── 05_robots_sitemap.png
```

## Steps followed

1. **Target selection** – Chose a public website (college / personal / org site) for passive recon.
2. **WHOIS lookup** – Ran `whois <domain>` on the Linux VM to get registrar, registration/expiry dates, and name servers.
3. **DNS enumeration** – Ran `dig <domain> A/MX/NS/TXT` to identify DNS records.
4. **Technology identification** – Checked page source in Firefox and used the Wappalyzer extension (cross-checked the `Server` header via `curl -I`).
5. **HTTP security headers** – Ran `curl -I <domain>` and checked for CSP, X-Frame-Options, X-Content-Type-Options, HSTS, Referrer-Policy.
6. **Robots.txt & sitemap** – Checked `/robots.txt` and `/sitemap.xml` via `curl` and browser.
7. **Report compilation** – Consolidated all findings into the Reconnaissance Report with a conclusion.

## Tools used

- `whois` (WHOIS lookup)
- `dig` (DNS enumeration)
- `curl` (headers, robots.txt, sitemap.xml)
- Firefox (technology fingerprinting)

## Note on scope

All activity in this task was **passive reconnaissance only**, performed against a publicly accessible website. No scanning, exploitation, or unauthorized access was attempted, per the task's ethical guidelines.
