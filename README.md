# Network Security Labs

Practical OPNsense firewall and Suricata IDS labs built while studying cybersecurity. This project documents network segmentation, NAT, traffic analysis, custom detection rules and alert tuning through test observations and selected screenshots.

## Repository Structure

| Lab | Focus | Documentation |
|---|---|---|
| 01 OPNsense Firewall | WAN, LAN and DMZ segmentation; firewall policy; NAT; traffic analysis | [Firewall lab](01-opnsense-firewall/README.md) |
| 02 Suricata IDS | Emerging Threats alerts; three custom signatures; troubleshooting and tuning | [IDS lab](02-suricata-ids/README.md) |

Each lab keeps its screenshots in an `evidence/` directory. The Suricata lab also includes the original [custom rules](02-suricata-ids/rules/custom-ids.rules). See the [publication review](docs/publication-review.md) for evidence coverage and file checks.

## Environment

| Component | Role / address |
|---|---|
| fw01 / OPNsense | WAN `198.18.3.245`; LAN `10.10.10.1/24`; DMZ/OPT1 `10.10.20.1/24` |
| client01 | LAN test client, `10.10.10.102/24` |
| web01 / Apache | DMZ HTTP server, `10.10.20.122/24` |
| Linux Mint / WireGuard | External lab access, `100.65.0.13` |
| Suricata | PCAP live IDS on LAN; `HOME_NET` set to the DMZ `10.10.20.0/24` |

## Findings and Evidence

The source reports testing on **5 November 2026**. Included firewall screenshots show NAT, permitted traffic and denied flows between segments. The IDS screenshot shows alerts for all three custom SIDs alongside Emerging Threats alerts.

The write-ups distinguish screenshot-supported observations, author-reported test results, interpretations and recommendations. Raw test scripts, terminal output and full configuration exports are not included. These results have not been independently reproduced during publication preparation.

The later IDS exercise added a narrow LAN-to-DMZ HTTP exception. The earlier blocked HTTP result describes the original firewall policy. Only custom SID `1000002` was reported as retested after Apply and a full reboot; the supplied screenshot predates that retest. Suricata operated in **IDS mode**, so alerts do not demonstrate IPS blocking or successful exploitation.

## Goal

Develop practical network security skills and explain how firewall policies and detection rules behave, including their limitations. This is a learning portfolio rather than a production deployment guide. Separate examination requirements I1–I3 were unavailable and are not claimed as completed.

## Authorized Educational Testing

Testing was performed in an authorized educational lab environment. Scans and detection exercises targeted the lab systems. The documented commands are provided to explain the work and should only be repeated on systems owned by the operator or covered by explicit authorization.

## Documentation Scope

Documentation is in English. Original course assignment sheets are not republished. Selected screenshots retain lab addressing and traffic details for technical context; credentials, private keys, VPN configuration and firewall backups are excluded. Publication preparation changed documentation and file organization only; it did not access or modify the lab environment.
