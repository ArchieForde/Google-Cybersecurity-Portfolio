# Incident Report of Network Traffic Analysis

## Objective

This portfolio showcases a Incident report of network traffic analysis that was completed during the Google Professional Cybersecurity Certificate program. This project demonstrate my ability to write techical reports outlining the incident that has occured, assess the risk, and provide information for rectification of the incident. The goal is to highlight skills relevant to roles in cybersecurity.

### Skills Learned

#### Network Traffic Analysis

- Analyzing DNS and ICMP logs to identify communication issues.
- Interpreting protocol-specific messages (e.g., “udp port 53 unreachable”).
- Using tools like tcpdump to capture and evaluate network traffic.

#### Incident Investigation

- Conducting a root cause analysis to determine potential sources of network failures.
- Identifying patterns in network behavior to isolate the issue.
- Providing possible explanations for incidents (e.g., Denial of Service attack or misconfiguration).

#### Understanding Network Protocols

- Deep knowledge of DNS, UDP, and ICMP protocols and their interactions.
- Recognizing port-specific issues (e.g., DNS on port 53).
- Understanding flags and error messages associated with protocols.

#### Packet Sniffing and Analysis

- Using packet capture tools like tcpdump to collect network data.
- Analyzing packet-level details to troubleshoot network issues.

#### Technical Writing and Communication

- Summarizing technical incidents clearly and concisely for stakeholders.
- Structuring incident reports with detailed explanations of the issue and analysis.
- Providing actionable next steps based on findings.

#### Problem Solving

- Formulating hypotheses for potential causes of the incident.
- Recommending steps to resolve issues (e.g., checking DNS server status or firewall rules).

#### Cybersecurity Awareness

- Identifying security vulnerabilities, such as susceptibility to Denial of Service attacks.
- Highlighting potential risks to systems and suggesting preventive measures.

#### Critical Thinking

- Evaluating multiple factors that could contribute to the incident.
- Making data-driven assumptions to pinpoint the root cause.


## Case Study

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.” 

log from tcpdump packet data

In the tcpdump log, you find the following information:

The first two lines of the log file show the initial outgoing request from your computer to the DNS server requesting the IP address of yummyrecipesforme.com. This request is sent in a UDP packet.

The third and fourth lines of the log show the response to your UDP packet. In this case, the ICMP 203.0.113.2 line is the start of the error message indicating that the UDP packet was undeliverable to port 53 of the DNS server.

In front of each request and response, you find timestamps that indicate when the incident happened. In the log, this is the first sequence of numbers displayed: 13:24:32.192571. This means the time is 1:24 p.m., 32.192571 seconds.

After the timestamps, you will find the source and destination IP addresses. In the first line, where the UDP packet travels from your browser to the DNS server, this information is displayed as: 192.51.100.15 > 203.0.113.2.domain. The IP address to the left of the greater than (>) symbol is the source address, which in this example is your computer’s IP address. The IP address to the right of the greater than (>) symbol is the destination IP address. In this case, it is the IP address for the DNS server: 203.0.113.2.domain. For the ICMP error response, the source address is 203.0.113.2 and the destination is your computers IP address 192.51.100.15.

After the source and destination IP addresses, there can be a number of additional details like the protocol, port number of the source, and flags. In the first line of the error log, the query identification number appears as: 35084. The plus sign after the query identification number indicates there are flags associated with the UDP message. The "A?" indicates a flag associated with the DNS request for an A record, where an A record maps a domain name to an IP address. The third line displays the protocol of the response message to the browser: "ICMP," which is followed by an ICMP error message.

The error message, "udp port 53 unreachable" is mentioned in the last line. Port 53 is a port for DNS service. The word "unreachable" in the message indicates the UDP message requesting an IP address for the domain "www.yummyrecipesforme.com" did not go through to the DNS server because no service was listening on the receiving DNS port.

The remaining lines in the log indicate that ICMP packets were sent two more times, but the same delivery error was received both times. 

Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

As an analyst, you can inspect network traffic and network data to determine what is causing network-related issues during cybersecurity incidents. Later in this course, you will demonstrate how to manage and resolve incidents. For now, you only need to analyze the situation. 

This event, in the meantime, is being handled by security engineers after you and other analysts have reported the issue to your direct supervisor. 

## Report

### Part One: Provide a summary of the problem found in the DNS and ICMP traffic log.

As part of the DNS protocol, the UDP protocol was used to contact the DNS server to retrieve the IP address for the domain name of yummyrecipesforme.com. The ICMP protocol was used to respond with an error message, indicating issues contacting the DNS server. The UDP message going from your browser to the DNS server is shown in the first two lines of every log event. The ICMP error response from the DNS server to your browser is displayed in the third and fourth lines of every log event with the error message, “udp port 53 unreachable.” Since port 53 is associated with DNS protocol traffic, we know this is an issue with the DNS server. Issues with performing the DNS protocol are further evident because the plus sign after the query identification number 35084 indicates flags with the UDP message and the “A?” symbol indicates flags with performing DNS protocol operations. Due to the ICMP error response message about port 53, it is highly likely that the DNS server is not responding. This assumption is further supported by the flags associated with the outgoing UDP message and domain name retrieval.

### Part Two: Explain your analysis of the data and provide at least one cause of the incident.

The incident occurred today at 1:24 p.m. Customers notified the organization that they received the message “destination port unreachable” when they attempted to visit the website yummyrecipesforme.com. The cybersecurity team providing IT services to their client organization are currently investigating the issue so customers can access the website again. In our investigation into the issue, we conducted packet sniffing tests using tcpdump. In the resulting log file, we found that DNS port 53 was unreachable. The next step is to identify whether the DNS server is down or traffic to port 53 is blocked by the firewall. The DNS server might be down due to a successful Denial of Service attack or a misconfiguration. 
