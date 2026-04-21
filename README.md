# 🚨 AI-Driven SOC Alert Automation using n8n

## 📌 Overview

This project implements a simplified Security Operations Center (SOC) automation workflow using n8n. It simulates real-world alert detection, enrichment, and response by integrating threat intelligence and automated alerting mechanisms.

---

## ⚙️ Workflow Architecture

```
Webhook → VirusTotal API → Decision Engine → Severity Classification → Alerts (Slack + Email)
```

---

## 🔍 Features

* Real-time alert ingestion via webhook
* Threat intelligence enrichment using VirusTotal API
* Automated severity classification (High / Medium / Low)
* Slack notifications for all alerts
* Email alerts for high-severity incidents
* Simulation of real-world attack scenarios

---

## 🧠 How It Works

1. Security event is sent to webhook (simulating SIEM alert)
2. IP address is extracted and checked via VirusTotal
3. Malicious score is evaluated
4. Alert is classified into severity levels
5. Alerts are sent:

   * Slack → all events
   * Email → high severity only

---

## 🛠️ Tech Stack

* n8n (Workflow Automation)
* REST APIs
* VirusTotal API
* Slack Webhooks
* SMTP (Gmail)
* JSON

---

## 📷 Screenshots

<img width="1917" height="932" alt="image" src="https://github.com/user-attachments/assets/16dfae7a-db81-4bcd-b516-36fde8ecc317" />
<img width="1917" height="714" alt="image" src="https://github.com/user-attachments/assets/d20055b7-2dd2-4641-8dc8-994524a14e5a" />



---

## 🚀 Setup Instructions

### 1. Install n8n

```
npm install -g n8n
n8n
```

### 2. Configure Webhook

* Create webhook node with POST method
* Path: `soc-alert`

### 3. Add VirusTotal API

* Sign up at https://www.virustotal.com
* Add API key in HTTP Request node

### 4. Configure Slack

* Create incoming webhook
* Paste URL in HTTP node

### 5. Configure Email

* Use Gmail SMTP
* Enable App Password

---

## 🧪 Sample Test

```
curl -X POST http://localhost:5678/webhook/soc-alert \
-H "Content-Type: application/json" \
-d "{\"source_ip\":\"8.8.8.8\",\"event\":\"failed_login\"}"
```

---

## 🎯 Outcome

This project demonstrates how SOC teams can automate alert triage, enrichment, and response using SOAR-like workflows, reducing manual effort and improving response time.

---

## 💡 Future Improvements

* Integrate SIEM tools (Splunk/Wazuh)
* Add dashboard visualization
* Implement auto-response (block IP)
* Add ML-based anomaly detection

---

## 👨‍💻 Author

Abhinay Dasi
