Lab 1: Vulnerability Assessment

In the vulnerability assessment lab, I learned how to take a large vulnerability scan and turn it into useful information instead of just trusting the scanner output.

I learned how to:

Review and prioritize vulnerabilities by CVSS score, KEV status, host role, and real-world risk.
Validate whether scanner findings are actually true by checking software versions and configurations.
Identify false positives instead of assuming every scanner finding is correct.
Recognize that a lower-CVSS vulnerability can be more important if it is actively exploited in the wild.
Use the CISA KEV catalog to improve prioritization.
Recommend specific fixes instead of simply saying “patch it.”
Suggest compensating controls when a vulnerability cannot be fixed immediately.
Think about scan cadence, especially for internet-facing systems.
Understand that vulnerability management is a process, not just a one-time scan.
See how delayed patching and infrequent scanning can allow a known vulnerability to remain exploitable.

The biggest lesson I learned was that a scanner gives me findings, but I have to determine which findings actually matter and what should be fixed first.

Lab 2: Digital Forensics / Incident Response

In the forensics and incident response lab, I learned how to reconstruct an attack from logs, files, authentication records, network traffic, and system activity.

I learned how to:

Build an incident timeline and determine when the attacker first appeared, gained access, escalated privileges, established persistence, moved laterally, and triggered an alert.
Identify the attacker’s path from reconnaissance → exploitation → webshell → root access → persistence → lateral movement → data staging/C2.
Analyze Linux authentication and system logs to identify pkexec privilege escalation, UID 0 backdoor accounts, malicious SSH keys, cron persistence, and systemd persistence.
Recognize malicious processes such as apache-worker and syslog-forward.
Understand why behavior-based detections are stronger than simple IP or hash detections.
Map attacker activity to MITRE ATT&CK tactics and techniques.
Build detection rules for persistence, webshell activity, exploitation, and lateral SSH movement.
Use the Pyramid of Pain to understand why attacker behavior is more valuable to detect than just hashes and IP addresses.
Identify gaps in detection coverage.
Build an eradication plan and recovery plan.
Understand the importance of credential and SSH key blast radius.
See how suspicious activity can exist in logs for hours without being acted on if proper alerting is missing.

