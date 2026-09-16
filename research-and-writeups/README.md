## Meridian Trust Bank Security Lab

This lab combined vulnerability assessment, digital forensics, incident response, and detection engineering into one end-to-end security investigation.

### What I Did

I began by reviewing vulnerability scan results across multiple Meridian Trust Bank systems. I validated scanner findings against actual software versions and system configurations, identified false positives, and reprioritized vulnerabilities using CVSS severity, asset exposure, and CISA KEV status.

I then investigated the compromise of `MTB-WEB01` by analyzing firewall logs, Apache logs, authentication logs, system logs, file-system timelines, recovered artifacts, and network activity.

From that evidence, I reconstructed the attacker’s activity from initial reconnaissance through:

* Exploitation of a public-facing Apache vulnerability
* Deployment of a web shell
* Privilege escalation to root using PwnKit
* Creation of a UID 0 backdoor account
* SSH key persistence
* Cron-based persistence
* Command-and-control beaconing
* Lateral movement to `MTB-FILE01`
* Systemd-based persistence on the second host
* Local data staging and suspected exfiltration activity

### Detection and Threat Analysis

I mapped the attacker’s behavior to the MITRE ATT&CK framework and created a consolidated IOC list containing malicious IP addresses, file paths, hashes, accounts, SSH keys, and persistence mechanisms.

I also used the Pyramid of Pain to distinguish between low-value indicators such as hashes and IP addresses and higher-value behavioral detections.

I developed detection logic for:

* Suspicious cron and systemd persistence
* Web shell activity
* Exploitation of public-facing applications
* Suspicious server-to-server SSH activity

### Incident Response

I created eradication and recovery plans covering:

* Removal of malicious files and persistence mechanisms
* Removal of unauthorized accounts and SSH keys
* Rotation of compromised credentials
* Patching of exploited vulnerabilities
* Hardening of Apache configuration
* Validation of clean backups
* Safe restoration of compromised systems
* Heightened post-incident monitoring

### Key Takeaways

This lab demonstrated how vulnerability management and incident response connect in practice. A vulnerability scanner can identify potential weaknesses, but those findings must be validated, prioritized, remediated, and monitored effectively.

It also reinforced the importance of behavior-based detections, proper credential management, network segmentation, patching cadence, centralized logging, and timely alerting.

Overall, the lab gave me hands-on experience moving through the full security lifecycle:

**Identify → Validate → Prioritize → Detect → Investigate → Contain → Eradicate → Recover → Improve**
