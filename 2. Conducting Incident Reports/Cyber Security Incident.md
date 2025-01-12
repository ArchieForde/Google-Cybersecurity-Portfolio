# Incident Report of a TCP SYN Flood Attack

## Objective

This portfolio showcases a Incident report of a TCP SYN Flood Attack that was completed during the Google Professional Cybersecurity Certificate program. This project demonstrate my ability to write techical reports outlining the incident that has occured, assess the risk, and provide information for rectification of the incident. The goal is to highlight skills relevant to roles in cybersecurity.

### Skills Learned

#### Understanding of TCP/IP Protocol Suite

- In-depth knowledge of the TCP three-way handshake and its role in reliable communication.
- Ability to analyze and interpret TCP-related logs and connection errors.
- Awareness of how TCP SYN Flood attacks exploit protocol vulnerabilities.

#### Attack Analysis

- Identification of attack types (e.g., TCP SYN Flood).
- Understanding of how malicious actors manipulate network protocols to disrupt services.
- Differentiation between legitimate and malicious network behavior based on log data.
  
#### Log Analysis

- Analyzing server logs to pinpoint anomalies such as suspicious IP addresses (e.g., 203.0.113.0).
- Interpreting logs to identify attack vectors and determine their impact on server functionality.
- Recognizing patterns of malicious behavior in network traffic.

#### Threat Mitigation

- Proposing practical defenses against attacks, such as configuring firewalls and behavior-based anomaly detection.
- Recommending strategies to prevent and manage Denial of Service (DoS) attacks, including resource allocation and server hardening.
- Emphasizing the importance of intrusion detection/prevention systems (IDS/IPS) in mitigating such incidents.

#### Understanding of Firewalls

- Knowledge of how firewalls can analyze and filter traffic based on IP addresses and behavior.
- Suggesting configurations to block malicious traffic, such as blocking specific IP addresses or monitoring for suspicious patterns.

#### DoS/DDoS Attack Knowledge

- Familiarity with different types of Denial of Service (DoS) attacks and their mechanisms.
- Understanding the distinction between DoS and Distributed Denial of Service (DDoS) attacks.
- Awareness of how such attacks can overwhelm server resources and disrupt functionality.
  
#### Packet Analysis

- Expertise in examining packets for unusual activity, such as repeated SYN packets without final acknowledgment.
- Proficiency with tools like Wireshark or tcpdump for monitoring and capturing network packets.
  
#### Network Security Best Practices

- Recognizing the importance of proactive measures such as rate limiting, SYN cookies, and other countermeasures to mitigate attacks.
- Awareness of modern security practices to safeguard against TCP SYN Floods and other network-level attacks.

## Case Study

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. 

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

## Report

#### Section 1: Identify the type of attack that may have caused this network interruption

One potential explanation for the website's connection timeout error message is a type of DoS attack (Denial of Service) known as a TCP SYN Flood which is where a malicious actor tries to flood the server with SYN packets while intentionally not sending the final ACK segment. Causing the server, if not properly equipped, to become overwhelmed with the amount of requests and timeout. The logs show that an unknown IPv4 address: 203.0.113.0 is causing this attack by sending empty SYN segments. This event could be managed by creating a firewall that properly analyses incoming IP addresses and behavioural anomalies to stop attacks like these happening.

#### Section 2: Explain how the attack is causing the website to malfunction

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:

1. First the client sends a segment with SYN (Synchronize) to the server requesting the start of the connection informs the server that the client is likely to start communication and with what sequence number it starts segments with

2. Next the server sends back a SYN-ACK (Synchronize-Acknowledge) segment to the      client. The ACK signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with.

3. Finally, the client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer.

This is known as a TCP SYN Flood where the threat actor sends a flood of SYN packets all at once while intentionally not sending the final ACK segment leaving the server waiting for a response that causes the server to use up resources for each of these half-opened connections. The log indicates that the IPv4 address: 203.0.113.0 is the cause of a TCP SYN Flood attack by flooding the server with empty requests which is causing the server to timeout as it is constantly waiting for acknowledgment not allowing any other clients to create connections.



