## Lab - Recommend Endpoint Security Measures  

In this lab, we will meet the following objectives:

**Objectives**
Part 1: Recommend Mitigation Procedures to Address Vulnerabilities

Part 2: Recommend an Endpoint Protection Product for a New Network

**Background / Scenario**
To provide security, professionals typically implement a number of network security measures that work together in a layered security approach. Firewalls and other devices protect the network perimeter from attack; however, it is always possible that threats can elude these defenses. Therefore, it is not only necessary to protect the network perimeter, but also take action to protect individual network hosts from compromise. In this lab, we will read two case studies and recommend endpoint threat mitigations that are appropriate to address the exploits.

**Required Resources**
Internet access

**Instructions**
Part 1: Recommend Mitigation Procedures to Address Vulnerabilities
You work on a security team for a manufacturing company. A new customer requires that, before the company can be granted the contract, it must comply with more stringent standards. A vulnerability assessment of the network was completed and a number of vulnerabilities were found, including the following endpoint security issues:

- The company uses supervisory control and data acquisition (SCADA) systems to monitor and control their manufacturing processes. 
- The SCADA software runs on the Windows XP operating system.
- Critical systems allow the use of unknown USB media.
- Users can access the network with personal computing devices such as smartphones, tablets, and laptops.
- Users are able to freely browse the WWW, including known malware sites.
- Inconsistent anti-virus software installed on hosts, included legacy versions with unknown signature update status.

Using the material covered in this course and additional information that you locate on the internet, complete the table below.


### **Part 1: Recommend Mitigation Procedures to Address Vulnerabilities**  

| **Issue**                                       | **Recommended Mitigation**                                                                                                                                                                   |  
|-------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| **Out-of-date operating system versions**       | Upgrade Operating systems to a modern and supported OS (e.g., Windows 10/11 with LTSC or Linux-based OS).|  
| **Critical systems allow use of USB media**     | Disable USB ports on critical systems or enable USB port control via group policies or endpoint security tools. Enforce encryption and whitelisting for USB devices using endpoint protection. |  
| **Use of personal computing devices on network**| Implement a **Bring Your Own Device (BYOD)** policy with Mobile Device Management (MDM) solutions to enforce security protocols such as encryption, anti-malware, and remote wipe capabilities. |  
| **Users are able to freely browse WWW**         | Enforce web browsing restrictions using a secure web gateway or DNS filtering services. Block access to known malicious sites and implement URL filtering.                                   |  
| **Antivirus issues**                            | Standardize antivirus solutions across all endpoints, ensuring that all hosts run up-to-date software with frequent signature updates and heuristic scanning for new threats.                 |  

---

### **Part 2: Recommend an Endpoint Protection Product for a New Network**
A friend has recently received venture capital funding for a promising new product. Rapid growth is predicted. He is opening a location for his startup and has asked you to help him with recommendations for endpoint security measures to implement in the new network.

Use your learning in the course and internet research to recommend a comprehensive endpoint security product. Keep in mind that the company is currently small, but will grow quickly. Provide reasons for your decision based on features of the product.

**Chosen Product**: **CrowdStrike Falcon**  

| **Feature**                                   | **Value**                                                                                                                                                  |  
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| **Cloud-based endpoint protection**           | Lightweight and scalable for a rapidly growing startup, eliminating the need for extensive on-premises infrastructure.                                      |  
| **Behavior-based detection**                  | Monitors endpoint behavior in real time, detecting and mitigating advanced threats such as ransomware or zero-day exploits.                                 |  
| **Device control**                            | Allows control of USB devices, reducing the risk of unauthorized peripherals introducing malware.                                                           |  
| **Threat intelligence integration**           | Provides detailed threat reports and context, enabling proactive security measures and informed decision-making.                                             |  
| **Ease of deployment and management**         | Intuitive interface with minimal configuration effort, making it suitable for small startups with limited IT staff.                                          |  
| **Scalability**                               | Scales with the company's growth, accommodating an increasing number of endpoints without significant overhead.                                              |  
| **Remote remediation**                        | Enables security teams to isolate compromised systems and remediate threats without disrupting business operations.                                          |  

---

**Conclusion**

In conclusion, addressing endpoint vulnerabilities and implementing robust security measures are critical components of a comprehensive cybersecurity strategy. By upgrading outdated operating systems, restricting USB access, enforcing BYOD policies, limiting web browsing, and standardizing antivirus solutions, organizations can significantly mitigate risks and enhance their overall security posture. Additionally, adopting an advanced endpoint protection product like CrowdStrike Falcon ensures scalable and proactive defense against evolving threats, while supporting rapid business growth.  

By applying **Critical Thinking and Problem Solving** to assess and address these issues, organizations can effectively protect their critical assets and ensure long-term operational resilience. This multi-layered security approach will provide resilience against vulnerabilities and protect critical systems from modern cybersecurity threats.  






