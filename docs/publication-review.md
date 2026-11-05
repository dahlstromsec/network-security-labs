# Publication Review

## Source and Preparation

Prepared on 5 November 2026 from `network-security-portfolio.zip`. Both numbered lab directories, all 16 firewall test observations and the Suricata technical findings were preserved. The four PNG screenshots and the custom rule file are byte-for-byte unchanged from the archive. The rule file was moved into `02-suricata-ids/rules/`.

The root README was rewritten as a portfolio overview with lab links, environment, evidence limits, learning goal and an authorized educational testing statement. Course titles were translated into English. An unsupported reference to VLANs was removed: the supplied material demonstrates routed network segments without establishing VLAN configuration. Ignore patterns were expanded for local credentials, captures and generated configuration.

## Evidence Coverage

| Evidence | What the supplied files establish | Limits |
|---|---|---|
| WAN/NAT screenshot | HTTP and SSH destination translations, VPN administrator pass entries and denied legacy port 2233 | Does not independently show HTTP 200, SSH authentication or the complete source restrictions |
| DMZ screenshot | DMZ-to-LAN denials, allowed HTTPS and DNS, denied outbound TCP 22/25 | Repeated rows can be retransmissions; they do not establish separate attacks |
| LAN screenshot | DNS/HTTP/HTTPS pass entries, permitted DMZ SSH, blocked DMZ HTTP and outbound TCP 25 | Does not show DNS response contents or HTTP status codes |
| IDS screenshot | Custom SIDs 1000001–1000003 and ET SIDs 2001219/2008538 with action `allowed` | Predates the reported tuning and reboot retests; proves neither exploitation nor IPS blocking |
| Custom rule file | Three source signatures; matches the rules printed in the IDS README | No Suricata binary was available for a fresh local syntax check |
| Historical test narrative | Author-reported connectivity results, setup, successful syntax check, tuning and persistence | Raw terminal output, scripts and complete configuration are absent; not independently reproduced |

The original firewall HTTP denial and later IDS HTTP exception describe different stages of the lab. The custom SSH rule counts matching SYN packets, not failed authentication. Only SID 1000002 was reported as reconfirmed after Apply and reboot. Production recommendations and interpretations are not presented as completed tests. Separate I1–I3 examination requirements remain outside the verified scope.

## File and Privacy Review

All ten publication files were inventoried. Text files were inspected for credentials, tokens, passwords, private key material, connection strings and sensitive configuration. All four screenshots were visually inspected, decoded and checked for metadata. No credentials, tokens, private keys, full configuration exports or VPN configuration were found. PNG metadata contains DPI information only.

The screenshots intentionally retain lab IP addresses, host references, ports, timestamps and rule labels. Firewall screenshots also contain ordinary public service destinations and IPv6 link-local identifiers; these can reveal network context and device-derived identifiers. These details are retained to preserve the supplied evidence. No image redaction was performed. Generic `fake` in the SSH example is a test username. `/root/ids-lab/` is a historical lab path, not a bundled credential or configuration export.

The review combined manual inspection and a targeted pattern scan; it is not a guarantee that every possible secret format is detectable. Ignore patterns reduce accidental inclusion of common sensitive files but do not replace reviewing future changes.

## Documentation Checks

All relative Markdown links and image targets were checked for existence and exact filename case. All four PNG files decoded successfully. The three rule lines were compared with the README code block and the archive original. No external Markdown links are used in the publication files.

## Scope of Preparation

Only the local publication copy was changed. The downloaded ZIP and actual lab environment were left untouched. No Git commit, push or GitHub repository creation was performed during preparation. Repository name proposed for approval: `network-security-labs`.

Presentation follows the numbered folders and concise project, structure and goal sections available in the existing Networking Handbook and Python for Cybersecurity repositories. GitHub API access was unavailable during preparation, so the general cybersecurity repository could not be fully compared. No license was added because the source archive does not specify one.

[Back to project overview](../README.md)
