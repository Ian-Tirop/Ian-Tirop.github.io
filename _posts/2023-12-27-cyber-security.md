---
layout: post
title: Cyber Security Exploration
subtitle: Understanding and Addressing Cyber Threats
categories: cybersecurity
tags: [scanning, case-study, cyber-kill-chain, ddos, digitalization, cybersecurity]
---
![cyberintro](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/0ac29ffc-35b7-43ce-8eec-dcff8ab3152a)

## Scanning Activity

In this section, we'll perform a basic scanning activity using standard tools such as traceroute, dig, and nslookup. Scanning is a fundamental aspect of cybersecurity that helps identify potential vulnerabilities and map network topologies.

### Traceroute Test

Traceroute (or tracert on Microsoft Windows systems) displays information about each “hop” a packet takes from your computer to the remote host.

On Microsoft Windows:

tracert example.com

On Apple MAC OS X and Linux

traceroute example.com

Tracerout result i achieved on Microsoft windows Using CMD for'google.com'.

![traceroutecmd](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/dbf80176-5cf6-4813-8e43-bf0ea7039676)
 
### Dig Test

Dig (on Mac OS X and Linux) and nslookup (on Microsoft Windows) are the primary command-line tools for troubleshooting DNS issues.

dig example.com

Dig Results

- **Name Server Records:** ns1.example.com, ns2.example.com
- **MX Records:** mail.example.com
- **Time-to-Live (TTL):** TTL for records Z seconds
 
### Nslookup Test

nslookup example.com

Nslookup Results i achieved on microsoft windows using CMD for'google.com

![nslookupcmd](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/1b925200-5cf1-4dcf-ba07-6f0d86e0bd11)

sample output view

- **IP Address Mapping:** X.X.X.X
- **Reverse DNS Lookup:** example.com
- **Domain Information:** Registrar: ABC Registrar, Registered on Date

### Cross-Tool correlation

Correlating results from all three tools provided a comprehensive view of the network. Interesting findings and potential security concerns include:

- **Mismatched Information:** Inconsistencies in IP addresses or domain information across tools may indicate a misconfiguration or a potential security risk.
- **Unexpected Open Ports:** Ports identified by Traceroute that were not corroborated by Dig or Nslookup could be indicative of unauthorized services or devices.
- **Domain and IP Address Alignment:** Ensure that the domain's IP address and associated records align correctly to prevent DNS-related attacks.

### Mitigations

NOTE: These are general strategies that can help reduce the risk at each stage. Actual mitigations may vary based on specific details. Based on the insights gained from the scanning activity, we'll discuss potential mitigations to address identified vulnerabilities. Mitigations may include recommendations for securing open ports, implementing firewall rules, or applying patches to eliminate potential points of exploitation. This step is essential for enhancing the overall security posture of the network.


## SolarWinds Breach Case Study

Let's dive into the SolarWinds breach case study based on the article by Temple-Raston (2021) and the Cyber Kill Chain model by Hutchins et al, 2011.

### Cyber Kill Chain Analysis

#### Phases Identification

Let's follow up how analysis the SolarWinds exploit using the Cyber Kill Chain was conducted with respect to the specific phases.

<table>
  <tr>
    <th>Cyber Kill Chain Phase</th>
    <th>Description</th>
    <th>Identification</th>
  </tr>
  <tr>
    <td>Reconnaissance</td>
    <td>Initial information gathering about the target</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Weaponization</td>
    <td>Creation of malicious payload or exploit</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Delivery</td>
    <td>Transmission of malicious payload to the target</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Exploitation</td>
    <td>Act of exploiting vulnerabilities to gain access</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Installation</td>
    <td>Installation of malicious components on the target</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Command and Control</td>
    <td>Establishment of communication for control</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Actions on Objective</td>
    <td>Execution of intended actions on the compromised system</td>
    <td>Yes</td>
  </tr>
</table>

#### Mitigations

Now, below is list of possible mitigations for each phase and what was achieved

<table>
  <tr>
    <th>Cyber Kill Chain Phase</th>
    <th>Description</th>
    <th>Possible Mitigations</th>
  </tr>
  <tr>
    <td>Reconnaissance</td>
    <td>Initial information gathering about the target</td>
    <td>
      <ul>
        <li>Security awareness training for employees</li>
        <li>Network monitoring</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Weaponization</td>
    <td>Creation of malicious payload or exploit</td>
    <td>
      <ul>
        <li>Email filtering</li>
        <li>Endpoint protection</li>
        <li>Threat intelligence</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Delivery</td>
    <td>Transmission of malicious payload to the target</td>
    <td>
      <ul>
        <li>Email filtering</li>
        <li>Web filtering</li>
        <li>Endpoint protection</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Exploitation</td>
    <td>Act of exploiting vulnerabilities to gain access</td>
    <td>
      <ul>
        <li>Regular software patching</li>
        <li>Endpoint protection</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Installation</td>
    <td>Installation of malicious components on the target</td>
    <td>
      <ul>
        <li>User privilege management</li>
        <li>Endpoint protection</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Command and Control</td>
    <td>Establishment of communication for control</td>
    <td>
      <ul>
        <li>Network monitoring</li>
        <li>Intrusion detection systems</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Actions on Objective</td>
    <td>Execution of intended actions on the compromised system</td>
    <td>
      <ul>
        <li>Incident response planning</li>
        <li>Data backup</li>
      </ul>
    </td>
  </tr>
</table>

#### Tools and Reasons

Now, let's identify the tools to utilize in each phase with reasons for each answer.

<table>
  <tr>
    <th>Cyber Kill Chain Phase</th>
    <th>Description</th>
    <th>Tools</th>
    <th>Reasons for Usage</th>
  </tr>
  <tr>
    <td>Reconnaissance</td>
    <td>Initial information gathering about the target</td>
    <td>
      <ul>
        <li>OSINT tools (e.g., Maltego)</li>
      </ul>
    </td>
    <td>Gather information about the target</td>
  </tr>
  <tr>
    <td>Weaponization</td>
    <td>Creation of malicious payload or exploit</td>
    <td>
      <ul>
        <li>Email security tools</li>
        <li>Endpoint protection tools</li>
      </ul>
    </td>
    <td>Filter malicious attachments and links; Detect and block malicious payloads</td>
  </tr>
  <tr>
    <td>Delivery</td>
    <td>Transmission of malicious payload to the target</td>
    <td>
      <ul>
        <li>Email security tools</li>
        <li>Web filtering</li>
        <li>Endpoint protection tools</li>
      </ul>
    </td>
    <td>Filter malicious emails and links; Block access to malicious websites; Detect and block malicious payloads</td>
  </tr>
  <tr>
    <td>Exploitation</td>
    <td>Act of exploiting vulnerabilities to gain access</td>
    <td>
      <ul>
        <li>Vulnerability scanning tools (e.g., Nessus)</li>
        <li>Endpoint protection tools</li>
      </ul>
    </td>
    <td>Identify and patch vulnerabilities; Detect and block exploitation attempts</td>
  </tr>
  <tr>
    <td>Installation</td>
    <td>Installation of malicious components on the target</td>
    <td>
      <ul>
        <li>Identity and access management tools</li>
        <li>Endpoint protection tools</li>
      </ul>
    </td>
    <td>Manage user privileges and access; Detect and block installation attempts</td>
  </tr>
  <tr>
    <td>Command and Control</td>
    <td>Establishment of communication for control</td>
    <td>
      <ul>
        <li>Network intrusion detection systems</li>
      </ul>
    </td>
    <td>Identify and block suspicious network activities</td>
  </tr>
  <tr>
    <td>Actions on Objective</td>
    <td>Execution of intended actions on the compromised system</td>
    <td>
      <ul>
        <li>Incident response tools</li>
        <li>Data backup tools</li>
      </ul>
    </td>
    <td>Facilitate a timely and effective response; Ensure data recovery in case of a successful attack</td>
  </tr>
</table>

#### views

The SolarWinds breach serves as a stark reminder of the sophisticated threats that organizations face in the digital age. The compromise of SolarWinds' software supply chain highlighted the vulnerability of even well-established and security-conscious entities. The incident underscores the critical importance of robust cybersecurity measures, continuous monitoring, and prompt incident response. As technology evolves, the cybersecurity landscape must adapt to mitigate emerging threats effectively.


## Distributed Denial of Service (DDoS)

### Introduction to Metasploit: A Powerful Penetration Testing Framework

Metasploit is an open-source penetration testing framework that provides a platform for developing, testing, and executing exploit code against a remote target. Developed in Ruby, Metasploit offers a comprehensive suite of tools for penetration testers, security researchers, and ethical hackers. Its modular architecture, extensive exploit database, and a wide range of supported platforms make it a go-to choice for professionals involved in assessing and fortifying the security of systems.

### Launching a DDoS Attack with Metasploit

In this experiment, we'll explore the process of conducting a Distributed Denial of Service (DDoS) attack using Metasploit. A DDoS attack floods a target server with a massive volume of requests, overwhelming its capacity and making it inaccessible to legitimate users.

 . **Step1:Setting up Metasploit**
   Ensure Metasploit is installed and accessible. You can open the Metasploit console by entering:

  ![ddos1](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/fd33a683-6eaa-4954-bbe2-6242d6d74ac5)
   
 . **Step 2: Selecting the Attack Module**
   In the Metasploit console, choose the auxiliary module for a TCP SYN flood attack:
   
  ![ddos2](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/1df92385-5f56-424d-8a8d-dfc1ea2c7210)

   View the available options:

   ![ddos3](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/988df700-cdf0-4be3-b247-902050b1d33b)
   
   
 . **Step 3: Configuring the Attack**
   Specify the target IP address, for instance, Apple's website:
   
![ddos4](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/f08645dc-3c68-44fd-b3e7-7960eba06489)

   Initiate the attack:
   
![ddos5](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/20089647-3c77-4426-aee0-4d6c8252339e)
   
   Note: If you encounter errors, consider the machine's compatibility and follow recommended configurations.
    
 . **Step 4: Outcome**
    While the experiment may encounter issues, a successful DDoS attack would not significantly impact the target website with only one 
    node generating requests. Additionally, the attacker's IP might get flagged temporarily.


### Conclusion.

This experiment delves into the realm of ethical hacking, specifically exploring the process of setting up a DDoS attack using Metasploit. It underscores the crucial importance of responsible and meticulous practices in cybersecurity, highlighting the need for careful configuration and adherence to recommended guidelines during security testing. The encountered error serves as a valuable lesson, emphasizing the significance of aligning the chosen environment with tool requirements. The experiment also underscores the responsibility that comes with ethical hacking, encouraging practitioners to make informed choices for accurate and reliable results. In essence, this exploration not only provides technical insights but serves as a reminder of the ethical dimensions inherent in cybersecurity, urging practitioners to approach security testing with a holistic and responsible mindset.


## Honeypot

### Unveiling Winbox Protocal Vulnerabilities: A honeypot Case Study

In this case study, we delve into building a honeypot for the Winbox protocol, a graphical user interface (GUI) application used to manage MikroTik RouterOS devices. The Winbox protocol has been a target for attackers, notably exploited by the infamous Meris botnet for large-scale DDoS attacks.

### Winbox Exploits: Reading and Writing System Files

Two vulnerabilities, allowing unauthorized reading and writing of crucial system files, are at the center of our analysis, with a focus on CVE-2018-14847. Attackers exploit this vulnerability to gain unauthorized access.

### Exploiting CVE-2018-14847 Step by Step

1. **Reading user.dat File:**
   - Attackers initiate the process by sending an open-file request to read the user.dat file.
   - The MikroTik device responds with the file size.
   - SYS_CMD set to 4 instructs the device to read the specified bytes from the file.
   - The device sends the content of the user.dat file, containing user credentials.
     
   ![honeypot1](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/65e1589b-0c43-43a2-97bf-0688c01f6334)

2. **SSH Access via "devel" Username:**
   - Recovered credentials enable attackers to create a file, enabling SSH access with the "devel" username.
   - The dissector captures the creation of the devel-login file.

   ![honeypot2](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/fef54c90-e7f2-4d4a-94fb-b0ebf9e8f17c)

3. **Post-Exploitation Actions:**
   - Once root shell access is acquired, attackers perform actions like enabling a VPN server and configuring scheduled tasks for 
     persistence.

### Setting Up a Winbox Honeypot

To mimic real-world scenarios, we deploy a honeypot for the Winbox protocol. Cowrie, acting as an SSH proxy, forwards traffic to the actual honeypot. MikroTik honeypots can be managed and dynamically created using Cowrie.

### Monitoring Winbox Protocol Interactions

Capturing interactions between attackers and the victim via the Winbox protocol is essential. While Cowrie manages SSH interactions, we employ pywinbox to log Winbox protocol commands, aiding in understanding attacker actions.

   ![honeypot3](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/69f739bb-26a4-4c0d-a8d9-f090b39251c1)

### pywinbox: Decoding Winbox Protocol

- **plaintext Protocol Management:** pywinbox decrypts Winbox packets, providing insights into attacker commands.
- **CVE-2018-14847 Exploitation Detection:** Logs all commands, acting as a medium interaction honeypot and forwarding traffic for high interaction.

### Conclusions

Understanding protocol intricacies is paramount for deploying effective honeypots. Security teams must comprehend specific protocols to configure honeypots accurately, attracting attackers and capturing malicious activity. Legal and ethical considerations are crucial to ensure compliance and prevent unintended harm.

Deploying honeypots provides valuable insights for proactive defense strategies, contributing to a more secure cyber landscape.



## Digitalization

![digitalization](https://github.com/Ian-Tirop/Ian-Tirop.github.io/assets/84772512/8f9acad8-fb72-4408-b8b8-4b989d1de65b)

A **fully digital enterprise**, defined by Wei et al. (2019), seamlessly integrates digital technology into every facet of its operations. While this transformation offers benefits like increased efficiency and innovation, it introduces new cybersecurity challenges, as outlined by Spremic and Simunic (2018).

### Cybersecurity Challenges for a Fully Digital Enterprise

1. **Increased Risk of Cyber Attacks:** Digitalization heightens vulnerability to threats like hacking, malware, and ransomware attacks.
   
2. **Interconnected Systems:** The interconnectivity of digital systems amplifies consequences, potentially impacting numerous stakeholders.

3. **Comprehensive Security Measures:** Effective security requires technical measures (firewalls, encryption) and policies enhancing employee awareness and training.

4. **Security Awareness and Training:** Lack of security awareness can pose a significant vulnerability.

### Cybersecurity Challenges for SMEs Transitioning to Digital

Transitioning to a digital enterprise poses unique challenges for bricks-and-mortar SMEs.

1. **Lack of Resources and Expertise:** SMEs may lack resources and expertise for robust cybersecurity during digital transformation.

2. **Budget Constraints:** Tight budgets may challenge allocating funds for cybersecurity, leaving SMEs vulnerable.

3. **Data Security:** Collecting and storing sensitive data requires strong data protection measures.

4. **Phishing and Social Engineering Attacks:** SMEs are susceptible to cybercriminals using phishing and social engineering tactics.

5. **Weak Authentication:** Inadequate password policies expose SMEs to unauthorized access.

6. **Third-Party Risks:** Relying on third-party vendors introduces security risks.

7. **Compliance Challenges:** SMEs may struggle to meet industry-specific compliance regulations.

8. **Insider Threats:** Risks from insider threats necessitate proper access controls and monitoring mechanisms.

9. **Patch Management:** Keeping software and infrastructure up to date is challenging for SMEs.

10. **Business Continuity:** Digital enterprises are susceptible to cyber incidents, making robust backup solutions crucial.

### Reflections on Cybersecurity in Light of the 'Energy Crisis'

While not explicitly addressing the energy crisis, the information underscores the importance of considering sustainability in the digital economy. Balancing the benefits of digital transformation with reducing energy consumption becomes crucial, especially in the context of the 2022 worldwide energy crisis.

This dual perspective emphasizes the need for organizations, whether fully digital enterprises or SMEs transitioning to digital, to fortify cybersecurity measures and align strategies with broader sustainability goals.


## Conclusion.
This post has explored various aspects of cybersecurity, including scanning activities, a case study on the SolarWinds breach, DDoS attacks, and the impact of digitalization. Stay tuned for more insights into the dynamic and evolving field of cybersecurity!


## References

1. Allen, J., Christie, A., Fischbacher, M., Garrett, R., Gray, D., Henderson, R., ... & Winstanley, A. (2021). Security Engineering: A Guide to Building Dependable Distributed Systems. (No specific link available)

2. Krebs, B. (2020). What We Know About the SolarWinds Hacking Campaign. Krebs on Security. 

3. Goodin, D. (2020). Russian hackers hit US government using widespread supply chain attack. Ars Technica. 

4. Cimpanu, C. (2021). Record-breaking DDoS attack hits AWS customers. The Record. 

5. Akamai. (2021). Q2 2021 State of the Internet / Security Report. Akamai. 

6. pitzner, L. (2003). Honeypots: Catching the Insider Threat. Network Security, 2003(7), 18-21. 

7. Provos, N., Holz, T., & McAlerney, J. (2008). Virtual Honeypots: From Botnet Tracking to Intrusion Detection. Pearson Education.
   
8. Wei, L., Zhang, X., & Mahrin, M. N. (2019). Digitalization and its effects on organizational knowledge management. In Handbook of Research on Knowledge Management for Contemporary Business Environments (pp. 1-27). IGI Global. 

9. Spremic, M., & Simunic, D. (2018). Cybersecurity challenges in the digital economy. Interdisciplinary Description of Complex Systems: INDECS, 16(3-B), 432-442. 
