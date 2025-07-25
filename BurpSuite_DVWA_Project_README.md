# 🔐 Web Application Pentesting using Burp Suite with DVWA (OWASP-BWA)

> A hands-on security testing project using **Burp Suite tools** against **DVWA** hosted inside **OWASP-BWA**.

---

## 📌 Objective

Perform vulnerability assessment and penetration testing on a deliberately insecure web application (DVWA) using **Burp Suite Community Edition**. Focus on core tools: Proxy, Repeater, Intruder, Decoder, Comparer.

---

## ⚙️ Lab Setup

| Component          | Configuration                                    |
|-------------------|--------------------------------------------------|
| Host OS           | Windows / Linux                                  |
| Virtualization    | VMware / VirtualBox                              |
| Attacker Machine  | Kali Linux                                       |
| Target Machine    | OWASP BWA (includes DVWA)                        |
| Target URL        | http://192.168.x.x/dvwa                          |
| Proxy Tool        | Burp Suite Community Edition                     |
| Browser           | Firefox (configured proxy: 127.0.0.1:8080)       |

---

## 🧰 Burp Suite Tool Usage

### 🔹 1. Proxy

- **Use**: Intercept and modify HTTP requests.
- **Scenario**: Intercept login request to DVWA.
- **Steps**:
  1. Turn "Intercept ON"
  2. Login to DVWA
  3. Capture and forward the request

📷 _Screenshot Placeholder_: `screenshots/proxy_login.png`

---

### 🔹 2. Repeater

- **Use**: Modify and replay HTTP requests.
- **Scenario**: Test multiple login credentials.
- **Steps**:
  1. Send request to Repeater
  2. Modify username/password
  3. Analyze response

📷 _Screenshot Placeholder_: `screenshots/repeater_login.png`

---

### 🔹 3. Intruder

- **Use**: Automate brute-force or fuzzing attacks.
- **Scenario**: Brute-force DVWA login form.
- **Steps**:
  1. Set payload markers for username/password
  2. Load password list
  3. Start attack and monitor response codes

📷 _Screenshot Placeholder_: `screenshots/intruder_attack.png`

---

### 🔹 4. Decoder

- **Use**: Encode/decode base64, URL, hex, etc.
- **Scenario**: Decode cookies or input data.

📷 _Screenshot Placeholder_: `screenshots/decoder_example.png`

---

### 🔹 5. Comparer

- **Use**: Compare two HTTP responses.
- **Scenario**: See difference between successful and failed login.

📷 _Screenshot Placeholder_: `screenshots/comparer_diff.png`

---

## 🔎 Example Vulnerability Tests

| DVWA Vulnerability     | Tool Used  | Test Example                        |
|------------------------|------------|-------------------------------------|
| SQL Injection          | Repeater   | `' OR '1'='1` in login fields       |
| XSS (Reflected)        | Repeater   | `<script>alert(1)</script>`        |
| Command Injection      | Repeater   | `; ls` or `& whoami`                |
| Brute Force Login      | Intruder   | Use common password list            |
| File Upload Bypass     | Repeater   | Rename `.php` to `.php.jpg`         |

---

## 📁 Folder Structure

```
BurpSuite-DVWA-Project/
├── README.md
├── screenshots/
│   ├── proxy_login.png
│   ├── repeater_login.png
│   ├── intruder_attack.png
│   ├── decoder_example.png
│   ├── comparer_diff.png
│   └── dvwa_page.png
└── wordlists/
    └── common_passwords.txt
```

---

## ✅ Conclusion

This project simulates real-world pentesting tasks using Burp Suite on DVWA. It helps develop manual testing skills like:
- Intercepting and modifying HTTP requests
- Brute-forcing logins
- Identifying XSS/SQLi
- Using tools like Decoder and Comparer effectively
