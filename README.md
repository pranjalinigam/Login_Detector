# 🕵️‍♂️ GhostLogin Detector  
A security-focused web system that detects **unauthorized, hidden, or suspicious login attempts** in real-time. It monitors devices, IP addresses, browser fingerprints, and login patterns to identify “ghost logins” — logins that occur without the user’s knowledge or through abnormal behavior.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Dataset & Inputs](#dataset--inputs)
- [Tools & Technologies](#tools--technologies)
- [Project Structure](#project-structure)
- [Core Features](#core-features)
- [What Makes It Stand Out](#What-Makes-It-Stand-Out)
- [Logic & Workflow](#logic--workflow)
- [User Interface & Design](#user-interface--design)
- [Strengths & Limitations](#strengths--limitations)
- [Recommendations & Future Work](#recommendations--future-work)
- [How to Run This Project](#how-to-run-this-project)
- [Author & Contact](#author--contact)

---

##  Overview
GhostLogin Detector is a web-based security system designed to track, analyze, and flag suspicious login behavior. It identifies abnormal patterns like unknown devices, IP mismatches, unusual timings, or bypassed interfaces—helping users and admins prevent account misuse or silent intrusions.

---

##  Problem Statement
Traditional login systems only validate credentials. They **do not detect**:
- Logins from unknown devices  
- Hidden/ghost login attempts  
- Suspicious IP or location changes  
- Login bypasses made through backend/API  

This project solves that gap by adding an **intelligent detection layer** that monitors and scores every login attempt.

---

##  Dataset & Inputs
No external dataset is required.  
Inputs are collected dynamically at login time:
- Email / Username  
- Password  
- Device metadata (browser, OS, device type)  
- IP address  
- Geo-location (optional)  
- Timestamp  
- Risk indicators (login frequency, unusual timing, etc.)

Logs are internally stored for analysis and review.

---

##  Tools & Technologies
**Frontend:** React / Vite  
**Backend:** Node.js + Express  
**Database:** MongoDB  
**Auth:** JWT / Sessions  
**Security:** Device Fingerprinting, IP Detection, Rate Limiting  
**Deployment:** Vercel / Render / Netlify  
**Version Control:** Git & GitHub  

---

##  Project Structure
ghostlogin-detector/
│
├── server/
│ ├── index.js # Express server
│ ├── middleware/
│ │ └── detectGhost.js # Core detection logic
│ ├── models/
│ │ └── LoginLog.js # Login logs schema
│ └── utils/
│ └── fingerprint.js # Fingerprint generator
│
├── client/
│ ├── src/
│ │ ├── components/
│ │ ├── pages/
│ │ ├── services/
│ │ └── App.jsx
│ └── vite.config.js
│
├── .env # Secrets, DB URI
├── package.json
└── README.md


---

##  Core Features
- 🔐 Real-time login monitoring  
- 🔍 Detection of ghost/hidden login attempts  
- 🌍 IP + Geo-location mismatch detection  
- 💻 Device & browser fingerprint tracking  
- ⚠️ Risk scoring based on user behavior  
- 📊 Detailed login logs for admin review  
- ✉️ Optional email/SMS alerts for suspicious logins  

---
##  What Makes It Stand Out 
- Proactive Security: Unlike traditional systems that only detect after breaches, GhostLogin Detector identifies threats before damage occurs.
- AI-Powered Detection: Uses machine learning to spot unusual login patterns, not just basic IP checks
- Cross-Platform Monitoring: Works for web and mobile apps seamlessly.
- Real-Time Alerts: Users get instant notifications about suspicious access, increasing accountability.
- Easy Integration: Can be added to any app using Auth0 and standard APIs, making it highly versatile.
- Unique Threat Visualization: Provides an interactive dashboard showing suspicious login locations, devices, and risk scores, giving users and admins clear insights at a glance.


---

##  Logic & Workflow
1. User enters login credentials.  
2. System captures:
   - Device fingerprint  
   - IP address  
   - Browser + OS details  
   - Timestamp  
3. The detector checks:
   - Device known or unknown?  
   - IP consistent with user history?  
   - Suspicious time/location?  
   - Login frequency abnormal?  
4. System generates a **risk score**.  
5. If the score is high:
   - Marks login as **GhostLogin / Suspicious**  
   - Logs entry  
   - Optionally alerts the admin  
6. User is either allowed, challenged (OTP), or blocked.

---

##  User Interface & Design
A clean and intuitive interface built using React:  
- Dashboard showing login history  
- Real-time alerts  
- Risk-level badges (Low / Medium / High)  
- Search & filter for logs  
- Highlighting suspicious entries  

Vite accelerates development with hot reload and fast builds.

---

##  Strengths & Limitations
### ✔️ Strengths
- Detects login anomalies in real time  
- Helps prevent unauthorized access  
- Lightweight and fast API  
- Easy integration with existing authentication systems  

### ❗ Limitations
- Requires consistent device fingerprint accuracy  
- Location/IP detection may fail on VPN/proxy  
- Risk scoring logic may need tuning per use case  

---

##  Recommendations & Future Work
- Add OTP challenge for high-risk logins  
- Add an admin dashboard with analytics  
- Improve ML-based anomaly detection  
- Integrate email/SMS notifications  
- Add user-level allowed-device management  
- Implement browser extension support  

---

##  How to Run This Project

### 1. Clone the repository
```bash
git clone https://github.com/your-username/ghostlogin-detector.git
2. Navigate into the folder
cd ghostlogin-detector

3. Install dependencies

For server:

cd server
npm install


For client:

cd ../client
npm install

4. Add environment variables

Create .env file in server/:

MONGO_URI=your_mongo_connection_string
JWT_SECRET=your_secret

5. Run the backend
cd server
npm run dev

6. Run the frontend
cd ../client
npm run dev
---

```
## Author & Contact

Created by Harshit

GitHub: https://github.com/harshitsr04

⭐ If you like this project, consider giving it a star on GitHub!
