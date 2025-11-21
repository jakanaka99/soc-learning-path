/*
# 🕵️‍♂️ INVESTIGATION #1  
# SUSPICIOUS EMAIL WITH MALICIOUS ZIP ATTACHMENT  
---

## 📌 ALERT SUMMARY — **SOC114: Malicious Attachment Detected – Phishing Alert**

| Field                 | Value                           |
|----------------------|---------------------------------|
| **Alert Type**       | SOC114 – Malicious Attachment Detected |
| **Severity**         | High                            |
| **Source Host**      | EmilyComp                       |
| **Source IP**        | 172.16.17.49                    |
| **Destination IP**   | 91.189.114.8                    |
| **Destination Host** | mogagrocol.ru                   |
| **Action**           | Allowed                         |
| **Rule Time**        | Mar 22, 2021 – 09:23 PM         |

---

# 🧪 INVESTIGATION STEPS

## 1️⃣ CONFIRM USER ACTIVITY

**Goal:** Determine whether the user interacted with the suspicious email or attachment.

**Actions Taken:**
- Reviewed **Email Security → Email Logs**
- Filtered logs for user *Emily*

**Findings:**
- Email was successfully delivered  
- **User did NOT open the email**  
- No link clicks  
- No attachment access events  

➡️ **User did not engage with the phishing attempt.**

---

## 2️⃣ ATTACHMENT ANALYSIS — MALICIOUS ZIP FILE

The email contained a **password-protected ZIP**, commonly used to bypass automated scanners.

**Actions Taken:**
- Downloaded the ZIP  
- Uploaded the ZIP file directly to **VirusTotal** (no extraction performed)

**Findings:**
- Multiple AV engines marked the file as **malicious**  
- Payload identified as malware  

➡️ **Attachment confirmed malicious.**

---

## 3️⃣ URL ANALYSIS — FAKE INVOICE PAGE

The email also included a suspicious URL.

**Actions Taken:**
- Submitted the URL to VirusTotal  
- Checked reputation with additional online tools  

**Findings:**
- URL leads to a **fake invoice download page**  
- Page serves the **same malicious payload**  
- VirusTotal identifies the domain as **malicious**

➡️ **URL confirmed malicious.**

---

## 4️⃣ ENDPOINT & NETWORK LOG REVIEW

Reviewed logs for user *Emily*, including:

- Browser activity  
- URL requests  
- File downloads  
- Outbound traffic  

**Findings:**
- No execution of the ZIP  
- No visits to the malicious domain  
- No suspicious traffic  
- No indicators of compromise  

➡️ **Endpoint remained clean and unaffected.**

---

# 📝 PLAYBOOK NOTES

- Email originated from an external sender  
- Password-protected ZIP used to bypass scanning  
- ZIP file flagged as **malicious** on VirusTotal  
- URL serves **malware**  
- User did not open or interact with the email  
- No endpoint indicators of compromise  

---

# ⚖️ ALERT CLASSIFICATION

## ✅ TRUE POSITIVE  
The email, attachment, and URL were malicious.  
However, no user interaction occurred, preventing compromise.

---

# ❗ ADDITIONAL NOTES

Due to LetsDefend limitations:  
- Full email body is not visible  
- Investigation relied on metadata, attachment analysis, URL reputation, and log review  

---

# ✔️ FINAL DETERMINATION

The alert was confirmed as a **true positive**.  
The email contained a **password-protected malicious attachment** and a **link leading to a fake invoice download page**.  
The ZIP file uploaded to VirusTotal received **multiple malicious detections**, and logs confirmed that the message was successfully delivered to the user's mailbox.  
**The sender and malicious URL have been blocked, and the email was removed from the user’s inbox.**

**No user interaction occurred and the endpoint shows no signs of compromise.  
Case closed.**
*/
