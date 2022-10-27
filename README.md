[![Sn1perSecurity](https://sn1persecurity.com/images/Sn1perSecurity-Attack-Surface-Management-header2.png)]


## Attack Surface Management
### Discover hidden assets and vulnerabilities in your environment

[![](https://sn1persecurity.com/wordpress/wp-content/uploads/2022/05/Sn1per-Enterprise-workspace-navigator1-3.png)]

## The ultimate pentesting toolkit.
See how Sn1per can help your security team

[![](https://sn1persecurity.com/wordpress/wp-content/uploads/2022/05/Sn1per-Enterprise-workspace-report1-3.png)](https://sn1persecurity.com/)

###  Automate the most powerful tools.
Security tools are expensive and time-consuming, but with Sn1per, you can save time by automating the execution of these open source and commercial tools to discover vulnerabilities across your entire attack surface.

[![](https://sn1persecurity.com/wordpress/wp-content/uploads/2022/05/Sn1per-Enterprise-host-list3-1.png)](https://sn1persecurity.com/)

### Find what you can't see.
Hacking is a problem that's only getting worse. But, with Sn1per, you can find what you can’t see—hidden assets and vulnerabilities in your environment. Integrate with the leading commercial and open source vulnerability scanners to scan for the latest CVEs and vulnerabilities. Find out quickly how hackers can attack your business or organization before it’s too late.

[![](https://sn1persecurity.com/wordpress/wp-content/uploads/2022/05/Sn1per-Enterprise-host-list2-1.png)](https://sn1persecurity.com/)

### Discover and prioritize risks in your organization.
Sn1per is a next-generation information gathering tool that provides automated, deep, and continuous security for organizations of all sizes.

[![](https://sn1persecurity.com/wordpress/wp-content/uploads/2022/05/Sn1per-Enterprise-vulnerability-report1-3.png)](https://sn1persecurity.com/)


## Kali/Ubuntu/Debian/Parrot Linux Install
```
git clone https://github.com/sweety519/S1
cd S1
bash install.sh
```

## AWS AMI (Free Tier) VPS Install
[![](https://sn1persecurity.com/wordpress/wp-content/uploads/2022/06/AWS-Marketplace.png)](https://aws.amazon.com/marketplace/pp/prodview-rmloab6wnymno)

To install Sn1per using an AWS EC2 instance:

1. Go to https://aws.amazon.com/marketplace/pp/prodview-rmloab6wnymno and click the “Continue to Subscribe” button
2. Click the “Continue to Configuration” button
3. Click the “Continue to Launch” button
4. Login via SSH using the public IP of the new EC2 instance

## Docker Install
[![](https://sn1persecurity.com/images/docker-logo.png)](https://hub.docker.com/r/sn1persecurity/sn1per)

From a new Docker console, run the following commands.
```
Download https://raw.githubusercontent.com/sweety519/S1/master/Dockerfile
docker build -t sn . 
docker run -it sn/bin/bash

```

## Usage
```
[*] NORMAL MODE
sniper -t <TARGET>

[*] NORMAL MODE + OSINT + RECON
sniper -t <TARGET> -o -re

[*] STEALTH MODE + OSINT + RECON
sniper -t <TARGET> -m stealth -o -re

[*] DISCOVER MODE
sniper -t <CIDR> -m discover -w <WORSPACE_ALIAS>

[*] SCAN ONLY SPECIFIC PORT
sniper -t <TARGET> -m port -p <portnum>

[*] FULLPORTONLY SCAN MODE
sniper -t <TARGET> -fp

[*] WEB MODE - PORT 80 + 443 ONLY!
sniper -t <TARGET> -m web

[*] HTTP WEB PORT MODE
sniper -t <TARGET> -m webporthttp -p <port>

[*] HTTPS WEB PORT MODE
sniper -t <TARGET> -m webporthttps -p <port>

[*] HTTP WEBSCAN MODE
sniper -t <TARGET> -m webscan 

[*] ENABLE BRUTEFORCE
sniper -t <TARGET> -b

[*] AIRSTRIKE MODE
sniper -f targets.txt -m airstrike

[*] NUKE MODE WITH TARGET LIST, BRUTEFORCE ENABLED, FULLPORTSCAN ENABLED, OSINT ENABLED, RECON ENABLED, WORKSPACE & LOOT ENABLED
sniper -f targets.txt -m nuke -w <WORKSPACE_ALIAS>

[*] MASS PORT SCAN MODE
sniper -f targets.txt -m massportscan

[*] MASS WEB SCAN MODE
sniper -f targets.txt -m massweb

[*] MASS WEBSCAN SCAN MODE
sniper -f targets.txt -m masswebscan

[*] MASS VULN SCAN MODE
sniper -f targets.txt -m massvulnscan

[*] PORT SCAN MODE
sniper -t <TARGET> -m port -p <PORT_NUM>

[*] LIST WORKSPACES
sniper --list

[*] DELETE WORKSPACE
sniper -w <WORKSPACE_ALIAS> -d

[*] DELETE HOST FROM WORKSPACE
sniper -w <WORKSPACE_ALIAS> -t <TARGET> -dh

[*] GET SNIPER SCAN STATUS
sniper --status

[*] LOOT REIMPORT FUNCTION
sniper -w <WORKSPACE_ALIAS> --reimport

[*] LOOT REIMPORTALL FUNCTION
sniper -w <WORKSPACE_ALIAS> --reimportall

[*] LOOT REIMPORT FUNCTION
sniper -w <WORKSPACE_ALIAS> --reload

[*] LOOT EXPORT FUNCTION
sniper -w <WORKSPACE_ALIAS> --export

[*] SCHEDULED SCANS
sniper -w <WORKSPACE_ALIAS> -s daily|weekly|monthly

[*] USE A CUSTOM CONFIG
sniper -c /path/to/sniper.conf -t <TARGET> -w <WORKSPACE_ALIAS>

[*] UPDATE SNIPER
sniper -u|--update
```

## Modes
* **NORMAL:** Performs basic scan of targets and open ports using both active and passive checks for optimal performance.
* **STEALTH:** Quickly enumerate single targets using mostly non-intrusive scans to avoid WAF/IPS blocking.
* **FLYOVER:** Fast multi-threaded high level scans of multiple targets (useful for collecting high level data on many hosts quickly).
* **AIRSTRIKE:** Quickly enumerates open ports/services on multiple hosts and performs basic fingerprinting. To use, specify the full location of the file which contains all hosts, IPs that need to be scanned and run ./sn1per /full/path/to/targets.txt airstrike to begin scanning.
* **NUKE:** Launch full audit of multiple hosts specified in text file of choice. Usage example: ./sniper /pentest/loot/targets.txt nuke.
* **DISCOVER:** Parses all hosts on a subnet/CIDR (ie. 192.168.0.0/16) and initiates a sniper scan against each host. Useful for internal network scans.
* **PORT:** Scans a specific port for vulnerabilities. Reporting is not currently available in this mode.
* **FULLPORTONLY:** Performs a full detailed port scan and saves results to XML.
* **MASSPORTSCAN:** Runs a "fullportonly" scan on mutiple targets specified via the "-f" switch.
* **WEB:** Adds full automatic web application scans to the results (port 80/tcp & 443/tcp only). Ideal for web applications but may increase scan time significantly.
* **MASSWEB:** Runs "web" mode scans on multiple targets specified via the "-f" switch.
* **WEBPORTHTTP:** Launches a full HTTP web application scan against a specific host and port.
* **WEBPORTHTTPS:** Launches a full HTTPS web application scan against a specific host and port.
* **WEBSCAN:** Launches a full HTTP & HTTPS web application scan against via Burpsuite and Arachni.
* **MASSWEBSCAN:** Runs "webscan" mode scans of multiple targets specified via the "-f" switch.
* **VULNSCAN:** Launches a OpenVAS vulnerability scan.
* **MASSVULNSCAN:** Launches a "vulnscan" mode scans on multiple targets specified via the "-f" switch.


