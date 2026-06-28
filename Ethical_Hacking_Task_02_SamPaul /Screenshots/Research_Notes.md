# Part E: Common Port Research

For each commonly seen port, here is the protocol it belongs to, what it's used for, and the
main security risks if it's left open or misconfigured.

## Port 20 / 21 — FTP (File Transfer Protocol)
- **Protocol:** TCP. Port 21 = control connection, Port 20 = data transfer.
- **Purpose:** Transferring files between a client and server.
- **Security Risks:** Sends credentials and data in plain text by default (no encryption), making
  it vulnerable to sniffing. Often allows anonymous login if misconfigured, and is a common
  target for brute-force attacks.

## Port 22 — SSH (Secure Shell)
- **Protocol:** TCP.
- **Purpose:** Secure remote login and command execution, and secure file transfer (SFTP/SCP).
- **Security Risks:** Generally secure due to encryption, but still a top brute-force target.
  Risks increase with weak passwords, default credentials, outdated SSH versions, or root login
  being enabled directly.

## Port 23 — Telnet
- **Protocol:** TCP.
- **Purpose:** Remote terminal access (legacy, largely replaced by SSH).
- **Security Risks:** Transmits everything — including login credentials — in plain text. Highly
  vulnerable to eavesdropping and man-in-the-middle attacks. Considered unsafe for any modern use.

## Port 25 — SMTP (Simple Mail Transfer Protocol)
- **Protocol:** TCP.
- **Purpose:** Sending email between mail servers.
- **Security Risks:** Can be abused for spam relay if the server is left "open relay."
  Misconfigured SMTP can leak internal usernames/server info through banner grabbing and verbose
  error messages.

## Port 53 — DNS (Domain Name System)
- **Protocol:** TCP/UDP (UDP for standard queries, TCP for larger responses/zone transfers).
- **Purpose:** Translating domain names into IP addresses.
- **Security Risks:** Vulnerable to DNS spoofing/cache poisoning, zone transfer misconfigurations
  (leaking internal network structure), and can be used as a vector for DDoS amplification
  attacks.

## Port 80 — HTTP (Hypertext Transfer Protocol)
- **Protocol:** TCP.
- **Purpose:** Serving unencrypted web traffic.
- **Security Risks:** No encryption means data (including form submissions, cookies, session
  tokens) can be intercepted in transit. Common target for web app attacks like SQL injection
  and XSS if the web app itself is vulnerable.

## Port 110 — POP3 (Post Office Protocol v3)
- **Protocol:** TCP.
- **Purpose:** Retrieving email from a mail server.
- **Security Risks:** Plaintext version sends credentials and email content unencrypted.
  Vulnerable to credential interception unless used over POP3S (SSL/TLS, port 995).

## Port 143 — IMAP (Internet Message Access Protocol)
- **Protocol:** TCP.
- **Purpose:** Retrieving and managing email on a mail server while keeping it synced across
  devices.
- **Security Risks:** Same issue as POP3 — plaintext IMAP exposes credentials and message
  content. Should be run over IMAPS (port 993) instead.

## Port 443 — HTTPS (HTTP Secure)
- **Protocol:** TCP.
- **Purpose:** Serving encrypted web traffic using TLS/SSL.
- **Security Risks:** Much safer than HTTP, but still vulnerable to outdated TLS versions, weak
  cipher suites, expired/misconfigured certificates, and the underlying web application's own
  vulnerabilities.

## Port 445 — SMB (Server Message Block)
- **Protocol:** TCP.
- **Purpose:** File and printer sharing on Windows networks.
- **Security Risks:** Historically one of the most exploited ports (e.g. the WannaCry/EternalBlue
  outbreak). Vulnerable to unauthorized access, lateral movement, and exploitation of unpatched
  SMB versions.

## Port 3389 — RDP (Remote Desktop Protocol)
- **Protocol:** TCP.
- **Purpose:** Remote graphical desktop access to Windows machines.
- **Security Risks:** Frequent target of brute-force and credential-stuffing attacks, especially
  when exposed directly to the internet. Vulnerable to exploits like BlueKeep if unpatched.

---

### Quick Reference Table

| Port | Protocol | Service | Key Risk |
|------|----------|---------|----------|
| 20/21 | TCP | FTP | Plaintext credentials |
| 22 | TCP | SSH | Brute-force, weak creds |
| 23 | TCP | Telnet | Fully plaintext |
| 25 | TCP | SMTP | Open relay / spam abuse |
| 53 | TCP/UDP | DNS | Spoofing, zone transfer leaks |
| 80 | TCP | HTTP | No encryption |
| 110 | TCP | POP3 | Plaintext credentials |
| 143 | TCP | IMAP | Plaintext credentials |
| 443 | TCP | HTTPS | Misconfigured TLS/certs |
| 445 | TCP | SMB | High-severity exploits (e.g. WannaCry) |
| 3389 | TCP | RDP | Brute-force, BlueKeep-type exploits |
