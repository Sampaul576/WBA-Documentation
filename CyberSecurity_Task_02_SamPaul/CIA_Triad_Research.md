# CIA Triad Research

The CIA Triad — **Confidentiality, Integrity, Availability** — is the foundational model used to guide security policies in any organization. Every control, tool, or policy in cybersecurity exists to protect one (or more) of these three pillars.

---

## 1. Confidentiality

**Definition:**
Confidentiality means ensuring that information is accessible only to people who are authorized to view it. It prevents sensitive data from being disclosed to unauthorized individuals, systems, or processes.

**Why it is important:**
Without confidentiality, sensitive data such as personal records, financial information, or trade secrets could be exposed to attackers, competitors, or the public — leading to identity theft, financial loss, legal penalties, and loss of trust.

**Real-world example:**
A hospital encrypts patient medical records so that only doctors and authorized staff can view them. If an attacker breaches the database but the data is encrypted, the records remain confidential even though access was technically gained.

---

## 2. Integrity

**Definition:**
Integrity ensures that data is accurate, consistent, and has not been altered or tampered with — either accidentally or maliciously — during storage, processing, or transmission.

**Why it is important:**
If data integrity is compromised, decisions made using that data (financial transactions, medical dosages, exam results) could be wrong or dangerous. Integrity is what makes data trustworthy.

**Real-world example:**
A bank uses checksums and digital signatures on transaction records so that if someone tries to alter the amount in a transaction, the system detects the change and flags it as invalid.

---

## 3. Availability

**Definition:**
Availability ensures that systems, applications, and data are accessible to authorized users whenever needed, without unnecessary downtime or disruption.

**Why it is important:**
If systems are unavailable — due to a cyberattack, hardware failure, or natural disaster — business operations stop, revenue is lost, and in critical sectors (healthcare, emergency services) lives can be at risk.

**Real-world example:**
An e-commerce website uses load balancers and backup servers so that even if one server crashes during a sale, customers can still access the site and make purchases.

---

## Comparison Table

| Aspect | Confidentiality | Integrity | Availability |
|---|---|---|---|
| **Goal** | Prevent unauthorized access | Prevent unauthorized modification | Ensure continuous access |
| **Protects against** | Data leaks, eavesdropping | Data tampering, corruption | Downtime, denial of service |
| **Common controls** | Encryption, access control, MFA | Hashing, checksums, version control | Backups, redundancy, failover systems |
| **Example threat** | Data breach | Man-in-the-middle attack | DDoS attack |
| **Real-world example** | Encrypted medical records | Digitally signed bank transactions | Load-balanced e-commerce servers |
