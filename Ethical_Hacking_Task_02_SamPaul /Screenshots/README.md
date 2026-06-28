# Ethical Hacking Task 02: Network Scanning & Service Enumeration

## Objective

This task covers the second phase of ethical hacking: **Scanning and Enumeration**. It focuses on
identifying active hosts, open ports, running services, and basic OS information using safe,
authorized methods — specifically against my own local machine / VM.

> All scans in this task were performed only against `localhost` (127.0.0.1) or my own VM,
> with explicit permission. No external or unauthorized systems were scanned.

## Folder Structure

```
Ethical_Hacking_Task_02_Rith/
├── README.md            -> this file
├── Scan_Report.md       -> full Nmap scan report (Parts B-G)
├── Research_Notes.md    -> Part E: common port research
└── Screenshots/         -> terminal screenshots for Parts A-D
```

## Tools Used

- **Nmap** (Network Mapper) — open-source tool for network discovery and security auditing
- Linux terminal (VM)

## Tasks Completed

| Part | Description | Status |
|------|-------------|--------|
| A | Install & verify Nmap | ✅ |
| B | Scan localhost — open ports | ✅ |
| C | Service version detection (`-sV`) | ✅ |
| D | OS detection (`-O`) | ✅ |
| E | Common port research | ✅ |
| F | Scan analysis | ✅ |
| G | Final scan report | ✅ |

## Summary

A full breakdown of commands, results, and analysis is in `Scan_Report.md`. Background research
on common network ports and their security risks is in `Research_Notes.md`. Raw terminal output
is captured in the `Screenshots/` folder.

## Key Takeaway

Scanning and enumeration are the foundation of any penetration test — you can't assess or secure
what you don't know exists. Nmap makes it possible to quickly map out open ports and running
services, which is the first real step toward understanding a system's attack surface.
