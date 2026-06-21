Weekly Breach Investigation
Breach: GentleKiller — EDR-Killing Framework by Gentlemen RaaS
Analyst: Jamal Mahmoad
Date: 2026-06-22

1. Executive Summary
The Gentlemen ransomware-as-a-service (RaaS) gang deployed a highly sophisticated framework called GentleKiller to systematically disable endpoint detection and response (EDR) tools before launching ransomware payloads.
GentleKiller includes at least eight in-house variants abusing vulnerable kernel drivers, plus three third-party EDR killers, forming one of the most advanced centralized suites ever seen in ransomware operations.
The framework targets 400+ processes across 48 security products, including Microsoft Defender, CrowdStrike, SentinelOne, Sophos, Palo Alto Networks, ESET, Bitdefender, Kaspersky, and McAfee/Trellix.

2. Attack Timeline

Late 2025: Gentlemen RaaS founded by hastalamuerte (ex-Qilin affiliate).
Q1 2026: Gentlemen among top five ransomware gangs globally.
Jan–Mar 2026: HavocKiller observed in intrusions.
May 2026: Internal leak confirms Gentlemen maintain GentleKiller suite.
June 17, 2026: ESET publishes detailed research on GentleKiller.

Exploitation Path:
BYOVD technique loads signed but vulnerable drivers.
Kernel-level termination of EDR/security processes.
Continuous loop scans and kills processes every 2 seconds.
Integration of third-party killers (HexKiller, ThrottleBlood, HavocKiller).
Credential theft via OxideHarvest stealer.

3. MITRE ATT&CK Mapping
Defense Evasion: Exploitation of Vulnerable Drivers (T1068), Masquerading (T1036)
Execution: Kernel-level Process Termination (T1106)
Credential Access: Credential Stealing from Browsers (T1555)
Persistence: Driver-based Implants (T1547)
Impact: Ransomware Deployment (T1486)

4. Detection Opportunities

Log Sources:
Kernel driver load events.
Process termination logs targeting security tools.
File system activity in GentlemenCollection staging directory.

Detection Rules:

Monitor for anomalous driver loads from non-standard vendors.
Correlate repeated process-kill loops every 2 seconds.
Detect binary protectors (Enigma/Themida) impersonating security vendors.

5. Recommended Mitigations
Enforce Microsoft Vulnerable Driver Blocklist.
Apply strict driver allowlisting policies.
Monitor for suspicious kernel driver activity.
Hunt for OxideHarvest credential theft indicators.
Educate defenders on BYOVD exploitation risks.

Analyst Notes
GentleKiller represents a strategic leap in ransomware operations, offering affiliates a centralized suite of EDR killers rarely seen even among top-tier gangs.
Gentlemen’s ability to weaponize public PoCs within days demonstrates a highly agile and well-resourced pipeline.
The combination of in-house and third-party tools, standardized through evasion layers, complicates attribution and detection.
With a 90% revenue share model, Gentlemen are aggressively expanding their affiliate base, making GentleKiller a growing threat across Southeast Asia, South America, and Western Europe
