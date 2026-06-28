# Ethical Hacking Task 01 – Reconnaissance Report

**Target type:** [PLACEHOLDER – College Website ]

---

## 1. Target Information (Part A)

| Field | Details |
|---|---|
| Website Name | [Kristu Jayanti College] |
| URL | [kristujayanti.edu.in] |
| Reason for choosing target | [Its my college website and i want to recon on it.] |

---

## 2. WHOIS Results (Part B)

Command used:
```
whois kristujayanti.edu.in
```

| Field | Value |
|---|---|
| Domain Name | [kristujayanti.edu.in] |
| Registrar | [ERNET India] |
| Registration Date | [2012-04-20T11:16:44.212Z] |
| Expiry Date | [035-04-20T11:16:44.212Z] |
| Name Servers | [REDACTED FOR PRIVACY] |
| Domain Status | [ok https://icann.org/epp#ok] |

📷 Screenshot: `Screenshots/01_whois_lookup.png`

---

## 3. DNS Information (Part C)

Commands used:
```
dig yourdomain.com A
dig yourdomain.com MX
dig yourdomain.com NS
dig yourdomain.com TXT
```

| Record Type | Value |
|---|---|
| A | [kristujayanti.edu.in.   60      IN      A       13.232.185.200] |
| MX | [kristujayanti.edu.in.   60      IN      MX      10 inbound-smtp.us-east-1.amazonaws.com.] |
| NS | [kristujayanti.edu.in.   60      IN      MX      10 inbound-smtp.us-east-1.amazonaws.com.] |
| TXT | [kristujayanti.edu.in.   60      IN      TXT     "google-site-verification=VOrsWwWwEhAGFZkrnd4U1jeqPgWzlFyoBiXUFBGL3ig"] |

📷 Screenshot: `Screenshots/02_dns_enumeration.png`

---

## 4. Technologies Identified (Part D)

Method used: Browser page source 

| Category | Finding |
|---|---|
| Web Server | [Apache/2.4.41 (Ubuntu)] |
| CMS | [No CMS detected] |
| Programming Language | [PHP — internal links use .php extensions (e.g., admission.php, history.php, message.php)] |
| JavaScript Framework | [Vanilla JavaScript only — no jQuery/React/Vue/Angular. Used for nav menu, image slider, FAQ chatbot, and modals] |
| CDN | [PAmazon CloudFront (cloudfront.net) — serves images and media] |

**Summary:** [The site runs on a custom PHP backend with no identifiable CMS, uses vanilla JavaScript for interactivity, and serves assets via AWS CloudFront. Tracking relies on Google Tag Manager plus dual Analytics tags (including a deprecated UA property). Several third-party tools (Zoom, Google Forms/Maps, TCS iON) support specific site functions.]

📷 Screenshot: `Screenshots/03_tech_identification.png`

---

## 5. Security Headers (Part E)

Command used:
```
curl -I https://yourdomain.com
```

| Header | Present (Yes/No) | Purpose |
|---|---|---|
| Content-Security-Policy (CSP) | No | [Restricts which sources (scripts, styles, images) the browser is allowed to load from, reducing the risk of cross-site scripting (XSS) attacks ]|
| X-Frame-Options | No | [Controls whether the page can be embedded in an `<iframe>` on another site, helping prevent clickjacking ]|
| X-Content-Type-Options | No | [Stops the browser from "MIME-sniffing" a file into a different content type than declared, reducing certain injection risks] |
| Strict-Transport-Security (HSTS) | No | [Forces the browser to only connect over HTTPS for a set period, preventing protocol-downgrade and man-in-the-middle attacks ]|
| Referrer-Policy | No | [Controls how much referrer (origin/URL) information is shared when a user navigates away from the page]

📷 Screenshot: `Screenshots/04_security_headers.png`

---

## 6. Robots.txt & Sitemap Findings (Part F)

URLs checked:
- `https://yourdomain.com/robots.txt`
- `https://yourdomain.com/sitemap.xml`

| Question | Answer |
|---|---|
| Does the website have a robots.txt file? | Yes |
| Does it have a sitemap? | Yes |
| What information can be learned from these files? | robots.txt shows which paths/directories the site owner has asked search engine crawlers not to index — this can sometimes hint at admin panels, staging areas, or internal tools. sitemap.xml lists the pages the site wants indexed, which gives a quick map of the site's structure and scope. On this target, requesting these files from the non-www domain (`kristujayanti.edu.in`) returned a `301 Moved Permanently` redirecting to `www.kristujayanti.edu.in`, confirming `www` as the canonical domain. The redirect response also disclosed the server stack: `Apache/2.4.41 (Ubuntu)`. |

📷 Screenshot: `Screenshots/05_robots_sitemap.png`

---

## 7. Overall Observations

[The biggest finding is that all five major security headers (CSP, X-Frame-Options, X-Content-Type-Options, HSTS, Referrer-Policy) are missing, leaving the site with no built-in defenses against clickjacking, MIME-sniffing, or downgrade attacks. The server also discloses its exact version (Apache/2.4.41 Ubuntu) in multiple responses, which is minor info leakage useful for narrowing down known vulnerabilities. DNS and CDN findings confirm the site is fully hosted on AWS — A record on AWS IP space, mail via Amazon SES, and CloudFront for content delivery — with no CMS detected, meaning it runs on custom PHP that won't receive the regular patches a platform like WordPress would get. The WHOIS expiry date also appears malformed and is worth double-checking, though it's likely just a formatting glitch rather than a real issue.]

---

## 8. Conclusion (150–200 words)

[Reconnaissance is the first phase of ethical hacking because every later step — scanning, exploitation, reporting — depends on the groundwork laid here. Before touching a system actively, you build a picture of it passively, using only publicly available information.This exercise taught me that even basic, non-intrusive lookups reveal a surprising amount. WHOIS confirmed who owns and registered the domain, DNS records exposed the hosting provider and mail infrastructure (AWS), the security header check revealed that none of the standard browser-level protections (CSP, HSTS, X-Frame-Options, etc.) were in place, and robots.txt/sitemap checks showed how the site is structured for crawlers.Passive recon is safer and more responsible than active scanning because it never sends unusual or potentially disruptive traffic to the target — it simply reads what's already public. But that doesn't make it harmless information: missing security headers, disclosed server versions, and hosting details are exactly what an attacker would use to plan a more targeted attack. This is why organizations should treat this kind of "harmless" public information seriously and fix what they can — even something as simple as adding missing headers closes a door before someone tries to walk through it.]

---

*This reconnaissance was performed using only publicly available, passive sources. No scanning or exploitation was carried out against the target.*
