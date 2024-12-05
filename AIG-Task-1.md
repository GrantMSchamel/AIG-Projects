# 🕵️‍♂️ AIG Cybersecurity Advisory: Apache Log4j Zero-Day Vulnerability

---

## **Challenge Scenario**

### **Introduction**  
As an Information Security Analyst at AIG, you are tasked with responding to emerging cybersecurity vulnerabilities to ensure the company remains protected. A recent zero-day vulnerability has been reported in Apache Log4j, one of the most commonly used logging libraries. This vulnerability has the potential to impact a variety of AIG's systems that utilize the affected Apache services. In this task, you will review the relevant Cybersecurity & Infrastructure Security Agency (CISA) advisories, identify affected systems, and draft a notification to the relevant infrastructure owners to mitigate the risk.

---

## **⚠️ Disclaimer**  
The details in this advisory are based on real-world security findings and are meant to simulate a practical exercise in vulnerability management.

---

## **🛠️ Task Objectives**

1. **Review the CISA advisory on Apache Log4j vulnerability.**
2. **Identify which infrastructure within AIG may be affected.**
3. **Draft a detailed advisory email to inform the relevant infrastructure owners about the zero-day vulnerability and its risks.**

---

## **📚 Research Summary: Apache Log4j Vulnerability (CISA Advisory)**  

The vulnerability in Apache Log4j, tracked as CVE-2021-44228 (Log4Shell), allows attackers to execute arbitrary code remotely by exploiting the improper handling of JNDI lookups in log messages. This vulnerability is particularly dangerous as it enables attackers to inject malicious payloads into log entries, resulting in remote code execution (RCE). Exploiting this vulnerability could lead to full system compromise, data exfiltration, and other severe security risks.

**CISA Advisory Recommendation:**
- Update Apache Log4j to **version 2.16.0** or higher, which disables JNDI lookups by default.
- Apply additional mitigations if immediate patching is not possible, such as restricting access to vulnerable systems and monitoring for abnormal network traffic.

---

## **🔍 Affected Infrastructure and Ownership**

### **Product Team**
- **Product Name:** Workstation Management System
- **Services Installed:** OpenSSH, dnsmasq, lighttpd
- **Potentially Affected Services:** None

### **Product Development Team**
- **Product Name:** Product Development Staging Environment
- **Services Installed:** Dovecot pop3d, Apache httpd, Log4j
- **Potentially Affected Services:** Apache httpd, Log4j

### **Marketing Team**
- **Product Name:** Marketing Analytics Server
- **Services Installed:** Microsoft ftpd, Indy httpd, Microsoft Windows RPC
- **Potentially Affected Services:** None

### **HR Team**
- **Product Name:** Human Resource Information System
- **Services Installed:** OpenSSH, Apache httpd, rpcbind2-4
- **Potentially Affected Services:** Apache httpd

**Who to Email**
- Reviewing this information, I concluded that the Product team was affected by this vulnerability due to their use of Log4j. Based on this conclusion, I drafted an advisory email to their team lead to discuss the steps they needed to take to correct this vulnerability.
---

## **📧 Advisory Email**

---

**From:** AIG Cyber & Information Security Team  
**To:** product@email.com  
**Subject:** **Urgent: Apache Log4j Zero-Day Vulnerability - Immediate Action Required**

---

**Body:**

Hello John Doe,

The AIG Cyber & Information Security Team is writing to inform you about a critical vulnerability in Apache Log4j, which may affect your **Product Development Staging Environment**. This vulnerability, identified as CVE-2021-44228 (Log4Shell), has been widely reported and can lead to remote code execution through the improper handling of JNDI lookups in log messages.

The Log4j vulnerability allows attackers to inject malicious code into log messages, potentially leading to full system compromise. We strongly advise that you immediately update Apache Log4j to **version 2.16.0** or higher, which disables JNDI lookups by default and mitigates the risk of exploitation.

The details of the vulnerability are as follows:
- **Vulnerability:** Remote Code Execution (RCE) due to improper handling of JNDI lookups in log messages.
- **Impact:** Full system compromise, unauthorized access to data, and potential disruption to services.
- **Affected Service:** Apache httpd, Log4j in your Product Development Staging Environment.

Please confirm that the necessary update has been applied and that any other mitigations, such as monitoring for abnormal activity, have been implemented. If you need assistance, feel free to reach out.

For further information, please refer to the CISA advisory: [CISA Advisory: Log4j Vulnerability](https://www.cisa.gov/news-events/alerts/2021/12/10/cisa-releases-cybersecurity-advisory-apache-log4j-remote-code-execution-vulnerability).

We appreciate your prompt attention to this matter.

Kind regards,  
AIG Cyber & Information Security Team  

---

## **🛠️ Tools Used**

- **CISA Advisory Resources:** For researching the latest vulnerability information and recommendations.  
- **Email Communication:** For alerting infrastructure owners about the critical vulnerability.  
- **Vulnerability Management Platforms:** For tracking and confirming patch deployment across systems.

---

## **🧠 Key Takeaways**

- Immediate response to zero-day vulnerabilities is essential for minimizing the risk of exploitation.  
- Collaboration between teams is crucial in ensuring that security patches are deployed swiftly.  
- Effective communication with infrastructure owners is key to protecting critical systems and data.  


