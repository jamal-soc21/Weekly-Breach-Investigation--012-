## Weekly Breach Investigation
![Alt Text](https://github.com/jamal-soc21/Weekly-Breach-Investigation--012-/blob/main/blackx.png))
Breach: GentleKiller — EDR-Killing Framework by Gentlemen RaaS
Analyst: Jamal Mahmoad
Date: 2026-06-22

Summary
Gentlemen RaaS deployed GentleKiller, a BYOVD-based framework that disables endpoint security tools before ransomware execution.
It combines eight in-house variants with three third-party killers, targeting 400+ processes across 48 security products.

Attack Flow

Vulnerable drivers loaded (BYOVD).
Kernel-level termination of security processes.
Continuous loop kills processes every 2 seconds.
Integration of HexKiller, ThrottleBlood, HavocKiller.
Credential theft via OxideHarvest.

MITRE ATT&CK

Defense Evasion: Vulnerable Drivers (T1068), Masquerading (T1036)
Execution: Kernel Process Termination (T1106)
Credential Access: Browser Credential Theft (T1555)
Persistence: Driver Implants (T1547)
Impact: Ransomware Deployment (T1486)

Mitigation
Enforce Microsoft Vulnerable Driver Blocklist.
Apply strict driver allowlisting.
Monitor kernel driver activity.
Hunt for OxideHarvest indicators.

Analyst Notes

GentleKiller shows a strategic leap in ransomware operations, offering affiliates a centralized suite of EDR killers.
Gentlemen’s ability to weaponize public PoCs within days highlights their agility and resources.
Their 90% revenue share model accelerates affiliate growth, making GentleKiller a rising threat across Southeast Asia, South America, and Western Europe
