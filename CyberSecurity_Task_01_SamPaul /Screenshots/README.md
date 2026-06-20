# Cyber Security Task 01: Personal Security Audit & Cyber Awareness Assessment

## Part A: Device Security Assessment

Security assessment performed on my personal Linux VM.

| Check | Command Used | 
|---|---|
| Operating System | `lsb_release -a`
| OS Version | `cat /etc/os-release`
| Kernel Version | `uname -r`
| Is the system updated? | `sudo apt update && apt list --upgradable` |
| Antivirus Installed? (Yes/No) | `clamscan --version`
| Firewall Enabled? (Yes/No) | `sudo ufw status verbose`

📸 *Screenshots of each terminal command output are included in screenshots folder.

## Part B: Password Security Review

**What makes a strong password?**
A strong password is long (ideally 12+ characters), uses a mix of uppercase and lowercase letters, numbers, and special characters, and avoids predictable patterns like keyboard sequences or personal details such as birthdays or names. The longer and more random a password is, the harder it becomes for attackers to guess or crack it using brute-force or dictionary-based methods.

**Why should passwords be unique?**
If the same password is reused across multiple accounts, a breach on one platform can give attackers access to every other account using that password. This is known as a "credential stuffing" attack, where leaked username/password pairs from one breach are automatically tried on other websites. Unique passwords for every account contain the damage to a single service if a breach occurs.

**What is Multi-Factor Authentication (MFA)?**
MFA is a security method that requires two or more independent forms of verification before granting access to an account — typically something you know (a password), something you have (a phone or hardware key), or something you are (fingerprint/face recognition). Even if a password is stolen, MFA prevents unauthorized access because the attacker would also need the second factor.

**What are the risks of password reuse?**
Reusing passwords means a single data breach can cascade across all of a person's accounts. Attackers use automated tools to test leaked credentials against banking, email, and social media platforms. Since email accounts are often used to reset other passwords, a compromised email with a reused password can lead to a complete takeover of someone's digital identity.

**My Password Policy (Best Practices):**
1. Use at least 12–16 characters for every password.
2. Combine uppercase, lowercase, numbers, and special characters.
3. Never reuse a password across multiple accounts or services.
4. Avoid using personal information (names, birthdays, pet names) in passwords.
5. Enable Multi-Factor Authentication (MFA) on every account that supports it.
6. Use a password manager to generate and store complex, unique passwords.
7. Change passwords immediately if a service reports a data breach.

---

## Part C: Online Account Security Check

Reviewed the following 3 accounts. **No actual passwords are shared below.**

| Account | MFA Enabled? | Strong Password? | Recovery Email Configured? |
|---|---|---|---|
| Google | `[YES]` | `[YES]` | `[YES]` |
| GitHub | `[YES]` | `[YES]` | `[YES]` |
| LinkedIn | `[YES]` | `[YES]` | `[YES]` |

## Part D: Cyber Threat Research

### 1. Phishing
**Definition:** Phishing is a social engineering attack where attackers send fraudulent messages — usually emails or texts — that appear to come from a trustworthy source, tricking victims into revealing sensitive information like passwords or credit card numbers.
**Real-world Example:** Attackers commonly send emails impersonating banks or delivery services, asking users to "verify their account" by clicking a link to a fake login page that captures their credentials.
**Prevention Methods:** Verify sender email addresses carefully, never click suspicious links, hover over links to check the real destination URL, and enable MFA so a stolen password alone isn't enough to gain access.

### 2. Malware
**Definition:** Malware (malicious software) is any program designed to damage, disrupt, or gain unauthorized access to a computer system. This includes viruses, worms, trojans, and spyware.
**Real-world Example:** A user downloads a "free" pirated software file that secretly installs spyware, allowing attackers to monitor keystrokes and steal personal data.
**Prevention Methods:** Only download software from official/trusted sources, keep the operating system and applications updated, use antivirus/anti-malware tools, and avoid opening unknown email attachments.

### 3. Ransomware
**Definition:** Ransomware is a type of malware that encrypts a victim's files, making them inaccessible until a ransom is paid to the attacker — though payment doesn't guarantee file recovery.
**Real-world Example:** The 2017 WannaCry attack infected hundreds of thousands of computers worldwide, encrypting files and demanding Bitcoin payments, severely disrupting hospitals and businesses.
**Prevention Methods:** Maintain regular offline backups of important files, keep systems patched and updated, avoid suspicious downloads/links, and use endpoint protection software.

### 4. Social Engineering
**Definition:** Social engineering is the psychological manipulation of people into performing actions or divulging confidential information, exploiting trust rather than technical vulnerabilities.
**Real-world Example:** An attacker calls an employee pretending to be IT support, convincing them to reveal their login credentials "for a system update."
**Prevention Methods:** Verify identities through official channels before sharing information, be skeptical of urgent or pressuring requests, and undergo regular security awareness training.

### 5. Data Breach
**Definition:** A data breach occurs when unauthorized individuals gain access to confidential data, such as personal records, financial information, or login credentials, often due to weak security controls.
**Real-world Example:** Large-scale breaches at major companies have exposed millions of users' emails and passwords, which are later sold or leaked on the dark web.
**Prevention Methods:** Use strong unique passwords, enable MFA, encrypt sensitive data, regularly monitor accounts for suspicious activity, and use breach-monitoring services like Have I Been Pwned.

---

## Part E: Cyber Security Awareness Poster

**Topic chosen:** Social Engin

Poster file included in this folder as: Social Eng

## Part F: Security Reflection

- *What cybersecurity risks did you identify in your own digital habits?*
- *What security improvements will you implement immediately?*
- *Why is cybersecurity important in today's world?*

**Draft starting point (edit/expand to reach 200–300 words and make it personal):**

> Going through this audit, I realized that some of my digital habits had gaps I hadn't paid much attention to before — such as  an account without MFA, an outdated system, a reused password. This task helped me see that even small oversights, like skipping a system update or reusing a password across platforms, can create real vulnerabilities that attackers actively look for.
>
> Going forward, I plan to immediately enable MFA on all my major accounts" / "set up a password manager" / "review my firewall settings regularly". These are simple changes that significantly reduce risk without requiring advanced technical knowledge.
>
> Cybersecurity matters today more than ever because so much of our personal, financial, and professional lives exist online. A single compromised account can lead to identity theft, financial loss, or reputational damage. As threats like phishing, ransomware, and social engineering become more sophisticated, individual awareness is often the first and most important line of defense — no firewall or antivirus can fully protect someone who unknowingly hands over their credentials. This task reinforced that cybersecurity isn't just a technical responsibility; it's a personal habit everyone needs to build.

---

## Folder Contents

```
CyberSecurity_Task_01_RithikRaj/
├── README.md                          (this file)
├── screenshot_partA_os_info.png
├── screenshot_partA_updates.png
├── screenshot_partA_firewall.png
└── awareness_poster.png
```
