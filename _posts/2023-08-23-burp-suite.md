---
layout: post
title: Burp Suite Overall
date: '2023-08-23 16:20:06 -0400'
categories: [Tools, Burp Suite]
tags: [pentesting, web,tools]
pin: false
math: true
mermaid: true
---
## Burp Suite Overview
Burp Suite is a software tool that helps cybersecurity experts and ethical hackers find security problems in websites and web applications. It works like a detective, looking for weak points that hackers could use to break into a website. It can check for things like secret information leaks, unprotected areas, and places where hackers might try to trick the website into doing something it shouldn't.

## Burp Community  Overview
There are different versions of Burp Suite available, and we'll be using the free Burp Suite Community edition for legal non-commercial purposes. While the Community edition has fewer features than the Professional one, it still offers valuable tools, including:

- **Proxy**: The well-known Burp Proxy lets us intercept and change requests and responses when dealing with web applications.
- **Repeater**: Another popular feature, Repeater, allows us to capture, modify, and resend requests multiple times. This is useful for tasks like trial-and-error payload creation in SQL injection or testing endpoint weaknesses.
- **Intruder**: In Burp Community, Intruder can send a series of requests to an endpoint, useful for bruteforce attacks or endpoint testing.
- **Decoder**: Though less commonly used, Decoder is handy for transforming data—decoding captured info or encoding payloads before sending them to the target.
- **Comparer**: The Comparer tool lets us compare two pieces of data at a word or byte level, helping speed up comparisons between potentially large data sets.
- **Sequencer**: Sequencer assesses token randomness (like session cookies) to uncover vulnerabilities stemming from weak random data generation algorithms.

## Burp Suite Download
Burp Suite is included in Kali Linux by default, eliminating the need for separate installation. In case it's missing, you can install it from Kali's repositories. For non-Kali systems, you can download installers from the <a target="_blank" href="https://portswigger.net/burp/releases/professional-community-2023-9-2?requestededition=community&requestedplatform="> Burp Suite Downloads page</a>.

## Starting Up Burp Suite
After launching Burp Suite and agreeing to the terms, a window prompts you to select the project type. In the Community edition, options are limited compared to Burp Pro. You can only proceed by clicking "Next". The following window lets you configure Burp Suite, with the default settings usually being suitable. Click "Start Burp" to open the main interface of Burp Suite.

## Burp Suite Dashboard
The Dashboard interface is divided into four sections:

- **Tasks Menu**: Here, you can set up background tasks for Burp Suite to execute while you work within the application. While the Pro version allows on-demand scans, the default "Live Passive Crawl" in the Community edition is well-suited for our module's purposes.

- **Event Log**: This section provides insight into Burp Suite's activities, such as starting the Proxy, and offers information about connections made through Burp.

- **Issue Activity**: Exclusive to Burp Pro, this section displays vulnerabilities identified by the automated scanner. In Burp Pro, vulnerabilities are ranked by severity and can be filtered based on the scanner's confidence in their validity. Feel free to close out of this panel for more room.

- **Advisory Section**: Offering more details about detected vulnerabilities, including references and suggested fixes, this section is valuable for understanding and addressing security issues. These details can also be exported into a report.

In Burp Suite, the default way to navigate the graphical user interface (GUI) is through the top menu bars. If you want to view multiple tabs separately, you can detach them into separate windows. To do this, go to the "Window" option in the top application menu, then select "Detach." You can later reattach these detached tabs using the same method.