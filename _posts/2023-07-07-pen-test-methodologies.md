---
layout: post
title: Penetration Testing Methodologies
date: '2023-07-07 14:55:22 -0400'
categories: [Penetration Testing]
tags: [pentesting]
pin: false
math: true
mermaid: true
---
## General Methodology
In a practical sense, a smart methodology is one that aligns with the specific situation at hand. For example, it wouldn't make sense to follow a methodology designed for testing web application security when you're actually trying to assess the security of a network.

Before exploring various industry-standard methodologies, it's important to note that they generally share a common framework comprised of the following stages:

### Information Gathering 

- Collection of extensive publicly accessible information about the target or organization. 
- Entails conducting open-source intelligence (OSINT) activities and in-depth research.
- The goal is to gather as much relevant information as possible about the target or organization.  

> This stage does not involve any form of system scanning or other intrusive actions.
{: .prompt-warning }

|   Tool                       | Description                                  |
|:-----------------------------|:---------------------------------------------|
|[**TBD**](https://rhettcoleman.github.io/categories/nmap/) |  TBD |

### Enumeration/Scanning

- The focus shifts to identifying the applications and services that are operational on the systems being assessed. 
- This includes the search for specific elements such as a potentially vulnerable web server.
- The goal is to uncover any potential weaknesses or vulnerabilities that could be exploited during the security assessment process.

|   Tool                       | Description                                  |
|:-----------------------------|:---------------------------------------------|
|[**Nmap**](https://rhettcoleman.github.io/categories/nmap/) |  Network scanning tool for discovering open ports, services, and gathering network information. |

### Exploitation

- This stage focuses on exploiting vulnerabilities identified in a system or application, which can be done using public exploits or by exploiting application logic.
- The goal is to leverage vulnerabilities in a system or application to gain unauthorized access, control, or privileges. 

|   Tool                       | Description                                  |
|:-----------------------------|:---------------------------------------------|
|[**TBD**](https://rhettcoleman.github.io/categories/nmap/) |  TBD |

### Privilege Escalation

- After successfully exploiting a system or application (known as gaining a foothold), expand access to the target system. 
 - This can be achieved through horizontal or vertical escalation. 
    + Horizontal escalation refers to accessing another account within the same permission group, such as another user.
    + Vertical escalation involves accessing an account in a different permission group, such as an administrator. 
 - The goal is to increase privileges and gain deeper control over the target system.

|   Tool                       | Description                                  |
|:-----------------------------|:---------------------------------------------|
|[**TBD**](https://rhettcoleman.github.io/categories/nmap/) |  TBD |

### Post-exploitation
- A crucial stage in the assessment process, encompassing several sub-stages:
1. Pivoting: Identifying and targeting other hosts within the network from the compromised system.
2. Gathering Additional Information: Leveraging privileged user access to collect further valuable information from the compromised host.
3. Covering Tracks: Taking measures to conceal evidence of the attack and ensuring that activities remain undetectable.
4. Reporting: Documenting the findings, detailing the actions taken, and providing a comprehensive report for further analysis and remediation.

|   Tool                       | Description                                  |
|:-----------------------------|:---------------------------------------------|
|[**TBD**](https://rhettcoleman.github.io/categories/nmap/) |  TBD |
