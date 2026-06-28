# Research Notes – Ethical Hacking Task 01

Short notes on the topics to study before the next session.

## Ethical Hacking Methodology
A structured approach a security professional follows when testing a system, so that work stays legal, repeatable, and doesn't accidentally cause damage. It generally moves from gathering information, to scanning, to (with permission) attempting access, then reporting findings.

## Penetration Testing Phases
Commonly broken into: Reconnaissance, Scanning, Gaining Access, Maintaining Access, and Covering Tracks/Reporting. Each phase builds on the previous one — recon results decide what's worth scanning, scanning results decide what's worth attempting, and so on.

## Passive vs Active Reconnaissance
Passive recon collects information without directly interacting with the target's systems — e.g. WHOIS, public DNS records, search engines, social media. Active recon involves direct interaction, like port scanning or sending probes, which is riskier and usually requires explicit authorization. This task only uses passive techniques.

## WHOIS
A protocol/service used to look up registration details for a domain name — who registered it, which registrar manages it, and when it was created and expires. It's useful for understanding who owns a domain and how long it's been around.

## DNS Basics
DNS translates domain names into IP addresses and other routing information. Key record types: **A** (maps a domain to an IPv4 address), **MX** (mail servers responsible for the domain), **NS** (name servers authoritative for the domain), **TXT** (arbitrary text, often used for verification or email security like SPF/DKIM).

## HTTP Security Headers
Response headers a web server can send to tell the browser how to handle the page more securely — e.g. blocking framing (clickjacking), restricting where scripts can load from (XSS), or forcing HTTPS. Missing headers don't always mean a site is insecure, but they reduce the browser-side protections available.

## Robots.txt
A plain-text file at the root of a site that tells search engine crawlers which paths they should or shouldn't index. It's a voluntary convention, not a security control — but it can sometimes reveal interesting paths (admin areas, staging directories) that the site owner didn't want indexed.

## Sitemap.xml
An XML file listing the pages of a site that the owner wants search engines to crawl. Useful during recon for quickly mapping a site's structure without manually clicking through it.

## Footprinting Techniques
Broader term for gathering information about a target organization — domains, IP ranges, employee names, technologies, social media presence — to build a picture before any testing begins. WHOIS, DNS enumeration, and technology fingerprinting (like in this task) are all footprinting techniques.
