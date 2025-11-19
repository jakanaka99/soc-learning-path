# 📧 Phishing Email Analysis

This document covers my approach to analyzing phishing emails, identifying malicious indicators, and validating whether an alert is a True Positive or False Positive.  
All steps shown here reflect what I actually do during real investigations inside LetsDefend.

---

## 🔍 Overview

When a *Phishing Email Detected* or *Malicious Attachment Detected* alert is triggered, my goal is to quickly determine:

- Was the email delivered to the user?
- Did the user open the attachment or click the link?
- Is the attachment or URL malicious?
- What indicators can be extracted (IP, hash, domain)?
- What actions should be taken to contain the threat?

I follow a consistent step-by-step process to ensure accuracy every time.

---

## 🛠 Tools & Sections Used

During analysis, I typically use:

- **Email Security** panel  
- **Log Management** (user activity logs)  
- **VirusTotal** (hash/URL analysis)  
- **Paybook** (If provided)  
- **Sandbox** (when file detonation is allowed)

---

## 📌 My Phishing Email Analysis Workflow

### **1️⃣ Verify Email Delivery**
- Check whether the email reached the user’s inbox.

### **2️⃣ Check User Interaction**
- Opened or not?
- Was a link clicked?
- Was an attachment opened?

Even if “Not Opened,” I still fully analyze the content.

### **3️⃣ Analyze Attachments**
- Extract file hash  
- Submit hash to **VirusTotal**  
- Review vendor detections  
- Note suspicious behaviors like password-protected zip files (common phishing tactic)

### **4️⃣ Analyze URLs**
- Extract URL(s)  
- Submit to **VirusTotal**  
- Check domain/IP reputation  
- Identify phishing pages, fake login portals, malware sites, etc.

### **5️⃣ Extract Indicators**
I document all IOCs, such as:

- Sender IP  
- Domains  
- URLs  
- File hashes  

These help with enrichment and future detection.

### **6️⃣ Determine if Alert is True/False Positive**
Based on:
- Email analysis  
- VT results  
- Logs  
- Delivery status  
- Attachment/URL behavior

I classify the alert.  
Most phishing alerts with malicious VT detections + email delivery = **True Positive**.

### **7️⃣ Recommended Actions**
Depending on findings:

- Block sender  
- Block URL/domain  
- Remove email from inbox  
- Notify affected user  
- Add IOCs to blocklist  
- Terminate machine if user downloaded/opened something

---

## 📁 Full Investigation Report

You can view my complete detailed analysis here:

[Investigation-1](./Investigation-1/)

Includes:
- Full alert analysis  
- Reasoning behind each decision  
- IOC extraction  
- Final verdict  
- Containment actions  

---

## ❗ Note About Completion Screenshot

Currently, I **cannot provide the completion screenshot** because the LetsDefend lab for that specific case does not allow me to use the lab more than once i dont know when the timer is going to be end.  
And some chapters require lab access that is temporarily restricted, so the final part of the investigation remains incomplete and the system doesn’t give the completion badge for that attempt.

I still documented everything I could based on the available data.

---

## ✅ Conclusion

This README summarizes how I investigate phishing emails using a real SOC workflow.  
For a complete example, please check **[Investigation-1] (./Phishing-Analysis/Investigation-1/) ** in the provided directory.

