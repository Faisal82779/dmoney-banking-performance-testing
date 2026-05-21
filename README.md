# 📚 DMoney — Banking Application Performance Test Suite

## 🚀 Project Overview

This project features a comprehensive performance testing suite for a digital financial service (MFS) platform, built using **Apache JMeter**. It simulates realistic user behavior under load for concurrent banking operations, validating system stability and integrity across three distinct transaction types: **Deposit**, **Send Money**, and **Payment**.

The collection incorporates token extraction mechanisms and integrates directly with the backend application's infrastructure. Dynamic variables handle automatic parameterization via external CSV datasets, while runtime financial amounts are dynamically generated to ensure production-realistic boundary scenarios without account balance depletion.

Strict response assertions are embedded within every load thread group to guarantee transaction validity and zero-fault execution.

---

## 🛠️ Technology Stack

| Tool / Technology | Purpose |
|------|---------|
| **Apache JMeter 5.6.3** | Load testing engine, script authoring, and execution |
| **Java (JDK)** | Runtime engine environment for execution |
| **MySQL Database** | Direct backend connectivity for dynamic transaction OTP retrieval |
| **CSV Data Set Config** | Dynamic injection of multi-user dataset profiles |
| **JMeter HTML Dashboard** | Visual test report, summary metrics, and aggregate analytics generation |

---

## ✨ Key Features

- 🏎️ **Automated MFA/OTP Bypass:** Utilizes direct JDBC database connections (`jdbc:mysql://localhost:3306`) to pull one-time transaction verification codes dynamically during execution.
- 🔐 **Dynamic Bearer Token Chains:** Processes authentication flows natively per user role using JSON Post Processors, injecting tokens dynamically into subsequent request headers.
- ⏱️ **Smooth Load Patterns:** Applies structured 120-second ramp-up curves per Thread Group to evaluate system behaviors during progressive traffic build-up.
- 🔄 **Isolation of Concerns:** Utilizes three structurally isolated thread groups mirroring core operational business flows.
- 🎲 **Controlled Financial Volatility:** Implements `Random Variable` controllers to generate safe transactional amounts bounded between \$10 and \$50.
- 📏 **Multi-Layer Assertions:** Validates functional integrity alongside response load behaviors using explicit JSON path match assertions.

---

## ▶️ How to Run

### 1. Prerequisites
- Ensure **Apache JMeter** is installed and configured in your environment system paths.
- Your local DMoney backend API engine (`localhost:5000`) and its underlying MySQL target instance must be live.

### 2. Execution via CLI (Recommended for HTML Dashboard generation)
```bash
jmeter -n -t dmoney.jmx -l reports/result.jtl -e -o reports/html-dashboard/
```

---

## 📊 Test HTML report

## Application Performance Index & Request Summary
<img width="1625" height="434" alt="Screenshot 2026-05-22 011758" src="https://github.com/user-attachments/assets/330eb65c-f25a-418b-bd60-219dba83e646" />

---

### Statistics

<img width="1639" height="788" alt="Screenshot 2026-05-22 011842" src="https://github.com/user-attachments/assets/6c5b3275-b60c-4208-9ee7-721cff342d8d" />

---
