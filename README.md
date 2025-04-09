# Penetration Testing Insights: RDP, Macro Exploits, and PHP Shell Uploads

**Author:** Mst. Awalunnisa  
**Student ID:** 242-56-002  
**Course:** CS516: Ethical Hacking  
**University:** Daffodil International University  
**Semester:** Fall 2024  
**Date:** November 2024

## Abstract

This project examines three major cyber exploitation techniques: RDP exploitation, malicious macros, and PHP backdoors via file upload vulnerabilities. It outlines how attackers exploit these weaknesses to gain unauthorized access and highlights effective mitigation strategies, including multi-factor authentication, disabling macros by default, and secure file validation. The project emphasizes proactive measures like regular patching, secure coding, and user education to enhance organizational cybersecurity.

## Acknowledgements

I extend my heartfelt gratitude to all who supported me in completing this project. Special thanks to N.M.I Raisul Bari, my teacher at Daffodil International University, for his invaluable guidance and feedback. I also appreciate the Department of Computer Science and Engineering for providing resources, and my family for their unwavering support.

## Table of Contents

1. [Introduction](#introduction)
2. [Background Information](#background-information)
3. [Exploitation Processes](#exploitation-processes)
4. [Conclusions and Recommendations](#conclusions-and-recommendations)
5. [Bibliography](#bibliography)

## Introduction

### Problem Statement

Cyberattacks have become more sophisticated, targeting system vulnerabilities such as RDP exploitation, macro-based exploitation, and PHP backdoors via file upload vulnerabilities. This project aims to analyze these techniques, assess the risks they pose, and propose practical solutions to mitigate their impact.

### Objective of the Project

- **Analyze Exploitation Techniques:** Investigate RDP, macro, and PHP backdoor file upload vulnerabilities.
- **Demonstrate Attack Mechanisms:** Showcase exploitation techniques and demonstrate how attackers gain unauthorized access.
- **Assess Security Risks:** Evaluate the potential risks, including unauthorized access, data theft, and system compromise.
- **Propose Mitigation Strategies:** Recommend best practices to prevent or minimize the impact of these exploits.
- **Enhance Cybersecurity Awareness:** Increase awareness of cybersecurity threats and encourage adoption of security protocols.

### Literature Review

- **RDP Exploitation:** Vulnerabilities like BlueKeep can lead to remote code execution, mitigated by strong passwords and multi-factor authentication.
- **Macro-Based Exploitation:** Malicious macros can spread malware through social engineering; mitigation includes disabling macros and user training.
- **PHP Backdoor via File Upload Vulnerabilities:** These attacks exploit file upload mechanisms to gain control; mitigation involves file validation and restricting script execution.

### Methodology Adopted

- Set up vulnerable environments for each attack type.
- Perform the attacks using appropriate tools.
- Analyze vulnerabilities and implement basic security measures to assess their effectiveness.

### Results

The project demonstrated that RDP, macro-based, and PHP backdoor attacks can gain unauthorized access to systems. However, implementing multi-factor authentication, disabling macros, and validating file uploads successfully mitigated these vulnerabilities.

## Background Information

### Overview of RDP, Macro, and File Upload Vulnerabilities

- **File Upload Vulnerabilities:** Attackers exploit improperly handled file uploads, leading to remote code execution and server compromise.
- **Office Macro Exploits:** Malicious macros in Office documents can execute malware on Windows systems when the user enables them.
- **RDP Exploitation:** RDP vulnerabilities like BlueKeep allow unauthorized access through brute-forcing weak credentials and exploiting unpatched systems.

### Importance in Cybersecurity

- Identifying vulnerabilities before exploitation.
- Strengthening security defenses.
- Reducing the risk of data breaches.

## Exploitation Processes

### 1. File Upload PHP Backdoor in DVWA

- **Environment Setup:** Configure DVWA and set the security level to "low."
- **Payload Creation:** Use `msfvenom` to generate a PHP reverse shell.
- **Exploitation:** Upload the payload to DVWA and use Metasploit to exploit the vulnerability.

**Remediations:**
- Validate file types.
- Rename uploaded files to prevent malicious extensions.
- Store files outside the web root.
- Disable PHP execution in the upload directory.

### 2. Macro-Based Exploitation in MS-Office

- **Payload Creation:** Use `msfvenom` to generate a reverse TCP payload.
- **Exploitation:** Write a macro script to trigger the payload execution when the document is opened.

**Remediations:**
- Disable macros by default.
- Use antivirus software to detect malicious macros.
- Apply security updates to Office applications.

### 3. Windows 11 RDP Exploitation

- **Exploitation Process:** Write a Python script to brute-force RDP credentials and gain access.
- **Remediations:**
  - Apply security patches.
  - Use multi-factor authentication and restrict RDP access using firewalls.
  - Monitor RDP sessions for unusual activity.

## Conclusions and Recommendations

### Conclusions

The project highlights the risks of RDP, macro, and PHP backdoor exploits and stresses the importance of proactive security measures.

### Recommendations

- Implement multi-factor authentication for RDP.
- Disable macros by default.
- Validate file uploads and restrict script execution.
- Conduct regular penetration testing.
- Educate users on security risks, including phishing.

## Bibliography

- Microsoft Security Advisory (2019). "CVE-2019-0708: Remote Desktop Protocol (RDP) Vulnerability." [Microsoft](https://support.microsoft.com/en-us/help/4500705).
- Symantec Threat Report (2020). "Macro-Based Malware in 2020: A Persistent Threat." [Symantec](https://www.symantec.com).
- OWASP Foundation (2020). "Top Ten Web Application Security Risks - File Upload Vulnerability." [OWASP](https://owasp.org/www-project-top-ten/).
- Kaspersky Lab (2020). "Web Application Security: PHP Backdoors and File Upload Exploits." [Kaspersky](https://www.kaspersky.com).
