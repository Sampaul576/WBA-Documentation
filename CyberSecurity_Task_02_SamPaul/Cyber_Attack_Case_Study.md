# Cyber Attack Case Study: WannaCry Ransomware

## What Happened?

In May 2017, the WannaCry ransomware attack spread rapidly across the world, infecting more than 200,000 computers in over 150 countries within just a few days. WannaCry exploited a vulnerability in Microsoft Windows called **EternalBlue**, which targeted the SMB (Server Message Block) protocol. Many of the affected systems were running outdated, unpatched versions of Windows. Once a machine was infected, WannaCry encrypted the user's files and displayed a ransom note demanding payment in Bitcoin in exchange for the decryption key.

One of the most affected organizations was the **UK's National Health Service (NHS)**, where the attack disrupted hospital operations, forcing staff to cancel appointments and surgeries and reverting some systems to pen-and-paper record keeping.

## Which Part of the CIA Triad Was Affected?

- **Availability** was the primary target — encrypted files and locked systems meant legitimate users could no longer access their own data or systems.
- **Confidentiality** was also affected to a degree, since attackers gained unauthorized access to systems before encrypting them.
- **Integrity** was indirectly impacted, as encrypted files were effectively altered from their original, usable state.

## What Was the Impact?

- Estimated global financial damage of **$4 billion+**.
- NHS hospitals had to cancel thousands of appointments and surgeries.
- Major organizations such as FedEx, Renault, and Telefónica experienced operational disruption.
- Loss of public trust in affected institutions, especially healthcare providers.

## How Could It Have Been Prevented?

1. **Timely patching** — Microsoft had already released a patch (MS17-010) for the EternalBlue vulnerability two months before the attack. Systems that applied it were not affected.
2. **Network segmentation** — Isolating critical systems would have limited the malware's ability to spread laterally.
3. **Regular backups** — Maintaining offline, regularly tested backups would have allowed organizations to restore data without paying ransom.
4. **Disabling unnecessary services** — Turning off outdated SMBv1 protocol where not needed would have removed the attack vector entirely.
5. **Employee awareness and endpoint protection** — Updated antivirus/EDR tools could have detected and blocked the malware before it spread.

*(Written based on publicly documented analysis of the WannaCry incident, in own words for this assignment.)*
