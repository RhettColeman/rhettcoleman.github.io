---
layout: post
title: Nmap Basics
date: '2023-07-06 11:07:28 -0400'
categories: [Tools, Nmap]
tags: [nmap, pentesting, scanning,tools]
pin: false
math: true
mermaid: true
---
## Nmap Overview
Nmap employs various techniques to scan and gather information about network hosts, such as IP addresses, open ports, running services, operating systems, and other related details. It operates by sending specially crafted packets to target hosts and analyzing the responses received.

Here are some key features:
- Port scanning: Nmap can scan a range of ports on a target system to determine which ports are open, closed, or filtered. This information helps in assessing the security posture of a network and identifying potential vulnerabilities.

- Host discovery: Nmap can determine which hosts are active on a network by using techniques like ICMP ping, TCP/IP handshake, ARP requests, and others. It helps in creating a comprehensive network map and identifying live systems.

- OS detection: Nmap can analyze the responses received from a target system to infer the operating system running on it. This information is valuable for security assessments and network inventory management.

- Service and version detection: Nmap can determine the services and their versions running on open ports. This allows administrators to identify outdated or vulnerable services and take appropriate actions to secure the network.

### Ports
Every computer has a total of 65,535 available ports; however, many of these are registered as standard ports.

The well-known ports range from 0 to 1023 and are assigned by the Internet Assigned Numbers Authority (IANA) for specific services. 

|  Port (TCP/IP)                   | Protocol        | Info |
|:-----------------------------|:-------------------|--------------:|
| Port 20/21 | FTP (File Transfer Protocol)    |  |
| Port 22 |  SSH (Secure Shell)   | |
| Port 23 |  Telnet   | |
| Port 25 |  SMTP (Simple Mail Transfer Protocol)  | |
| Port 53 |  DNS (Domain Name System)   | |
| Port 80 |  HTTP (Hypertext Transfer Protocol)   | |
| Port 110 |  POP3 (Post Office Protocol version 3)   | |
| Port 143 |   IMAP (Internet Message Access Protocol) | |
| Port 443 |   HTTPS (HTTP Secure) | |
| Port 3389 |  RDP (Remote Desktop Protocol) | |

## Manual

```bash
man namp
```

## Scanning Syntax
### Basic Syntax
```bash
nmap scantype options target
```
> `nmap` and `target` are required. `scantype` and `options` are optional.
{: .prompt-info }

> Not specifying a `scantype` will perform a default scan known as a "vanilla" or `SYN` scan.
{: .prompt-info }

### Scan Type
When port scanning with Nmap, there are four basic scan types.

|   Command                   | Description          | Info |
|:-----------------------------|:-------------------|--------------:|
|-sT | TCP Connect Scans   | Scan TCP Ports |
|-sS | SYN "Half-open" Scans   | Stealth Scan TCP Ports |
|-sU | UDP Scans  | Scan UDP Ports |
|-sn | ICMP Network Scan  | Maps the Network |

Example
```
nmap -sT 10.10.83.119
```
#### More on UDP Scanning
Due to this difficulty in identifying whether a UDP port is actually open, UDP scans tend to be incredibly slow in comparison to the various TCP scans. For this reason it's usually good practice to run an Nmap scan with --top-ports <number> enabled. 

```
nmap -sU --top-ports 20 <target>
```

If a UDP port doesn't respond to an Nmap scan, what will it be marked as `open|filtered`

#### More on ICMP Network Scanning (Mapping)
When initially connecting to a target network in a black box assignment, our primary objective is to create a network map or diagram that outlines the network's structure. This entails identifying IP addresses that correspond to active hosts and distinguishing them from inactive ones.

One way to do this is by using Nmap to perform a so called "ping sweep".

This is done with `-sn` and the IP address range.
> IP ranges which can be specified with either a hypen (-) or CIDR notation
{: .prompt-info }
```
nmap -sn 192.168.0.1-254
```
```
nmap -sn 192.168.0.0/24
```
### Options

> Capitalization matters in the Nmap scan syntax.
{: .prompt-info }

|   Command                   | Description          | Info |
|:-----------------------------|:-------------------|--------------:|
|-O | Operating System Scan  | Enable operating system detection |
|-p | Specify ports or port ranges to scan  | ex: -p 1-100 |
|-p- | Scan all ports | |
|-A | Enable aggressive scan options  | A very loud scan |
|-v | Increase verbosity level for more detailed output  | Gives more details |
|-vv | Increase verbosity level to level two  | Gives even more details |
|-script | Activate a script  | From the nmap scripting library |

Scans can be combined
```
nmap -sT -p 1-100 -O -vv 192.168.10.1
```

## Exporting Results
Nmap provides various options for exporting scan results to different formats, allowing you to analyze and share the output data more effectively. Here are some methods for exporting scan results.

|   Command                   | Description          | Info |
|:-----------------------------|:-------------------|--------------:|
|-oN | Normal Output  | Save the scan results in a human-readable format|
|-oG | Grepable Output  | Export the scan results in a greppable format|
|-oX | XML Output | Save the scan results in XML format|

> Export syntax can be combined with `scantype` and `option` syntax
{: .prompt-tip }

- Normal Output (`-oN`): Using the `-oN` option followed by a filename, you can save the scan results in a human-readable format.
```bash
nmap -oN scan_results.txt <target>
```
- Grepable Output (`-oG`):  The `-oG` option allows you to export the scan results in a greppable format. This format is suitable for parsing and further processing with tools like grep.
```bash
nmap -oG scan_results.gnmap <target>
```
- XML Output (`-oX`): The `-oX` option enables you to save the scan results in XML format, which is widely supported and can be easily parsed by various tools.
```bash
nmap -oX scan_results.xml <target>
```
- Combined Example
```bash
nmap -sT -p 8012 -oN scanresults.txt 10.10.165.160
```

