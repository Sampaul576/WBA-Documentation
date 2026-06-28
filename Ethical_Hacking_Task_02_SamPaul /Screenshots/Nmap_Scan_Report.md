# Nmap Scan Report

**Task:** Ethical Hacking Task 02 — Network Scanning & Service Enumeration
**Target System:** localhost / own VM (authorized self-scan only)

## Part A: Nmap Installation

**Command:**
```bash
nmap --version
```

**Output:**
```
[Nmap version 7.95 ( https://nmap.org )
Platform: x86_64-pc-linux-gnu
Compiled with: liblua-5.4.7 openssl-3.5.4 libssh2-1.11.1 libz-1.3.1 libpcre2-10.46 libpcap-1.10.5 nmap-libdnet-1.12 ipv6
Compiled without:
Available nsock engines: epoll poll select]
```

📷 Screenshot: `Screenshots/part_a_install.png`

---

## Part B: Scan Your Local Machine

**Command:**
```bash
nmap localhost
```

**Results:**

- **Total Open Ports:** `[Zero]`

📷 Screenshot: `Screenshots/part_b_scan.png`

## Part C: Service Version Detection

**Command:**
```bash
nmap -sV localhost
```
**Results:**
| Port | Service | Version |
|------|---------|---------|
| N/A  | N/A     | No open ports detected |

**Note:** The `-sV` scan confirms all 1000 scanned TCP ports on localhost (127.0.0.1) are closed. Since no ports are open, Nmap has no services to perform version detection on. This indicates no listening services (web server, SSH, database, etc.) are currently running on this machine.

📷 Screenshot: `Screenshots/part_c_service_version.png`

---

## Part D: Operating System Detection

**Command:**
```bash
sudo nmap -O localhost
```

**Was the OS detected?** `Inconclusive`
**Which OS was identified?** `Not identified — Nmap reported "Too many fingerprints match this host to give specific OS details," inconclusive on loopback (127.0.0.1). This is expected/common when scanning localhost, since loopback interfaces don't generate the same TCP/IP stack quirks Nmap uses for fingerprinting on a real network path.`
**Why is OS detection useful during penetration testing?**
> OS fingerprinting helps a tester understand which known vulnerabilities, exploits, and default
> configurations are likely to apply to a target. It narrows down the attack surface — for
> example, an outdated Windows server has very different known weaknesses than a Linux server —
> and helps prioritize which attack vectors to test first.

📷 Screenshot: `Screenshots/part_d_os_detection.png`

---

## Part E: Common Port Research

See `Research_Notes.md` for the full breakdown of FTP, SSH, Telnet, SMTP, DNS, HTTP, POP3, IMAP,
HTTPS, SMB, and RDP — protocol, purpose, and security risks for each.

---

## Part F: Scan Analysis

**1. Which services are currently running?**
> Based on the nmap scans performed (`-sV`, `-O`), no services were found running on localhost — all 1000 scanned TCP ports returned closed/reset. No listening services (web, SSH, database, etc.) were detected on this machine at the time of scanning.

**2. Are all open ports necessary?**
> Not applicable here — no open ports were found in these scans, so there are no unnecessary ports to flag. If Part B/C of your documentation showed open ports from an earlier scan (e.g., a different target or before a service was stopped), reference those specific results instead.

**3. Which services could become security risks if misconfigured?**
> While no ports were open during this scan, common services that pose risks if misconfigured generally include: SSH (port 22) — risky if weak passwords or root login are allowed; HTTP/HTTPS (80/443) — risky if running outdated web server software or exposing admin panels; FTP (21) — risky due to unencrypted credential transmission; and database ports (e.g., 3306, 5432) — risky if exposed externally without authentication. Refer to Research_Notes.md for the specific risks tied to any ports your earlier scans (Part B/C) actually found open.

**4. Which port would you disable if it wasn't required?**
> Since no ports were open in this scan, there isn't a specific port to disable here. As a general practice, any port running a service not actively needed (e.g., FTP on 21, or an old Telnet service on 23) should be disabled to reduce attack surface. If Part B/C identified a specific open port, name that port and justify disabling it based on its actual use case.

---

## Part G: Scan Report Summary
| Field | Detail |
|---|---|
| Scan Date | `28 June 2026` |
| Target System | localhost / Kali GNU/Linux Rolling |
| Commands Used | `nmap --version`, `nmap localhost`, `nmap -sV localhost`, `sudo nmap -O localhost` |
| Open Ports | `None — all 1000 scanned TCP ports were closed/reset` |
| Running Services | `None detected — no listening services found on scanned ports` |
| Operating System | `Inconclusive — Nmap reported "Too many fingerprints match this host to give specific OS details" when run against loopback (127.0.0.1)` |
| Observations | `No open ports or services were found, which is expected on a clean machine with no servers running. OS detection failed on loopback, likely because scanning 127.0.0.1 doesn't generate the typical network-stack behavior Nmap relies on for fingerprinting.` |
| Recommendations | `No immediate action needed since no exposed services were found. As a general practice, periodically re-scan after installing new services to confirm only required ports are open, and consider scanning against the VM's actual network IP (rather than loopback) for more reliable OS detection results in future tests.` |

### Conclusion

[Running Nmap against my own machine during this phase gave me a much clearer picture of what "enumeration" actually means in practice, beyond just reading about it. Scanning localhost showed that all 1000 commonly checked TCP ports were closed, meaning no services were actively listening and exposed on this system at the time of testing. Service version detection (`-sV`) and OS fingerprinting (`-O`) reinforced this, with the OS scan returning an inconclusive result, likely due to the limitations of fingerprinting over a loopback interface rather than a real network path.What stood out to me was realizing how much enumeration relies on a target actually exposing something to probe; a "clean" result is still meaningful information, since it confirms the attack surface (at least over TCP) is minimal. This connects directly to Task 01's reconnaissance work: where WHOIS, DNS, and HTTP header analysis gathered intelligence about external-facing infrastructure, this phase showed how the same enumeration mindset applies locally, scanning a host to understand exactly what it's running. Both reinforce that thorough enumeration always comes before deciding where to focus deeper testing.]
