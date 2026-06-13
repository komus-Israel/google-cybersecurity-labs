# PASTA Threat Modeling Case Study: E-Commerce Sneaker Platform
**Framework:** PASTA (Process for Attack Simulation and Threat Analysis)  
**Project Scope:** Threat modeling for a Sneaker E-Commerce Platform
**Status:** Completed
[The Google Doc Project Report](https://docs.google.com/document/d/1jnVn_rbDEBVlyxhM1PeLo8UelOQ_jiqT0lfarWiNTiw/edit?usp=sharing).

---

## 🎯 Project Overview
The business is preparing to launch a mobile app that makes it easy for their customers to buy and sell shoes. 

I performed a threat model of the application using the PASTA framework. Using each of the seven stages of the framework, I identified the security requirements for the new sneaker company app.

---

## 🏗️ The 7-Step PASTA Analysis breakdown

### Step 1: Define business and security objectives
* **Business Goals:** Smooth user experience for onboarding, authentication and account management. Proper payment handling during checkout

* **Security & Compliance Bounds:** Maintain PCI-DSS compliance for payment processing.

### Step 2: Define Technical Scope
Mapped the attack surface across the entire application ecosystem, identifying key assets:
* **Technologies Used:** APIs, Public Key Infrastructure, SHA-256, SQL.

### Step 3: Decompose Application

* **Data flow:** [Diagram](https://docs.google.com/presentation/d/1ol7y79popTFfNHM-90ES-H-i1Lpd0YNvPShxBlXozjg/template/preview?resourcekey=0-DZAkf7Vzh2PXsP-j3oXV-g)


### Step 4: Threat Analysis
* **Session Hijacking:** Attackers targeting the cookie/token management ecosystem to steal valid user session identifiers.
* **SQL Injection (SQLi):** Malicious inputs supplied to search bars, checkout fields, or inventory filters aimed at manipulating backend database queries to read, modify, or delete sensitive data.

### Step 5: Vulnerability Analysis
* **No Prepared Statements (SQL injection Vector)** 
* **Database Connections Not Closed** 

### Step 6: Attack Modeling 
Simulated malicious actor paths using attack trees to verify the exploitability of identified vulnerabilities.
* **Attack tree:** [Diagram](https://docs.google.com/presentation/d/1FmWLyHgmq9XQoVuMxOym2PHO8IuedCkan4moYnI-EJ0/template/preview?usp=sharing&resourcekey=0-zYPY7AhPJdcClXamlAfOag)

### Step 7: Risk Analysis & Impact
1. **Password Policy** 
2. **Principle of Least Privilege (PoLP)** 
3. **Data Protection (Encryption & Hashing)** 
4. **Code Hardening (Prepared Statements)**
5. **Resource Management**
---