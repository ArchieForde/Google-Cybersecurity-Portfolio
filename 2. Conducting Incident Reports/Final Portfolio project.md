# Final Incident Report using the NIST Cybersecurity Framework to respond and rectify.

## Objective

This portfolio showcases a the final Incident report of using the NIST CSF (National Institute of Standards and Technology's Cybersecurity Framework) that was completed during the Google Professional Cybersecurity Certificate program. This project demonstrate my ability to write techical reports outlining the incident that has occured, assess the risk, and provide information for rectification of the incident using a national framework. The goal is to highlight skills relevant to roles in cybersecurity.

### Skills Learned

#### System Hardening

- Recommended and implemented multi-factor authentication (MFA), strong password policies, and firewall maintenance to enhance system security.
- Developed strategies for preventing brute force attacks, ensuring secure user access, and reducing password-sharing risks.
  
#### Password and Authentication Policies

- Created robust password policies, including complexity rules, failed login attempt limits, and frequent password updates.
- Integrated MFA to add additional layers of security for verifying user credentials.
  
#### Application of NIST Cybersecurity Framework (CSF)

- Used the NIST CSF to identify vulnerabilities and align strategies to its core functions: Identify, Protect, Detect, Respond, Recover.
- Prioritized mitigation strategies based on NIST guidelines to address critical security risks.
  
#### Firewall Configuration and Maintenance

- Recommended proactive measures like reviewing and updating firewall configurations to prevent attacks.
  
#### Security Recommendations and Justifications

- Articulated the importance of enforcing preventive measures to mitigate vulnerabilities.
- Provided actionable solutions and communicated their benefits effectively to stakeholders.


## Case Study

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack. 

To address this security event, the network security team implemented: 

A new firewall rule to limit the rate of incoming ICMP packets

Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets

Network monitoring software to detect abnormal traffic patterns

An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security. 

Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats. 

Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections. 

Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process. 

Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident. 

## Report

### Section 1: Select up to three hardening tools and methods to implement

Three hardening tools the organization can use to address the vulnerabilities found include: 
Implementing multi-factor authentication (MFA)
Setting and enforcing strong password policies
Performing firewall maintenance regularly

MFA requires users to use more than one way to identify and verify their credentials before accessing an application. Some MFA methods include fingerprint scans, ID cards, pin numbers, and passwords. 

Password policies can be refined to include rules regarding password length, a list of acceptable characters, and a disclaimer to discourage password sharing. They can also include rules surrounding unsuccessful login attempts, such as the user losing access to the network after five unsuccessful attempts. 

Firewall maintenance entails checking and updating security configurations regularly to stay ahead of potential threats

### Section 2: Explain your recommendations

Enforcing multi-factor authentication (MFA) adds an additional layer of security beyond a password. It will reduce the likelihood that a malicious actor can access a network through a brute force or related attack since additional effort is required to authenticate in more than one way. MFA may also reduce the likelihood of people sharing passwords. Since the recipient of the shared password would need to possess additional authentication besides a password, MFA makes it less useful to share passwords, thereby making passwords less likely to be shared.

Creating and enforcing a password policy within the company will make it increasingly challenging for malicious actors to access the network. Policies such as suspending the account after a certain number of logins can prevent successful brute force attacks. Increasing password complexity, requiring more frequent password updates, and not allowing passwords to be reused also help stall malicious actors from infiltrating the network. 





