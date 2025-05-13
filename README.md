**IOC 10 – Conclusion / README**
Title:
Hidden Parameter Exploitation via Admin Override – Stealth Privilege Escalation Without Credential Use

Objective:
To analyze a fileless privilege escalation attack where the adversary exploited an undocumented administrative override parameter (admin_override=true) to bypass standard authentication and gain elevated access without triggering any alert or logging trail through normal access controls.

Key Findings:

Undocumented logic flaw: Attacker used a hidden HTTP parameter to trigger backend override behavior in /admin/login.

No failed logins or audit trail: Logs showed neither credential failure nor success, highlighting broken audit coverage.

Spoofed User-Agent string: Helped attacker avoid detection by rule-based filters.

Post-access command execution: Local user created through native server-side execution—confirmed via host system logs.

Unmonitored access control file: roles.json was altered or vulnerable, allowing attacker to persist changes to privilege rules without alert.

Tactical Value:
This case reinforces the importance of:

Monitoring undocumented behaviors and internal debug logic

Correlating low-noise access with post-auth privilege changes

Using cross-system triage (application + host logs) to close audit gaps

Treating invisible entries with real-world outcomes as critical indicators
