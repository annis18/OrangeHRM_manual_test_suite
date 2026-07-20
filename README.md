# 🧪 Manual Quality Assurance & Defect Tracking Portfolio
**Application Under Test:** [OrangeHRM Live Demo](https://opensource-demo.orangehrmlive.com/)  
**Module Tested:** Authentication & Login Security Workflows  
**Author:** [Animesh Singh Chauhan] 

---

## 📌 Project Overview
This repository contains an end-to-end Manual Quality Assurance (QA) testing suite executed against the **OrangeHRM Live** Enterprise Human Resource Management application. The project demonstrates industry-standard black-box testing methodologies, structured test case design using mathematical decision tables, comprehensive defect logging, and full requirement traceability.

---

## 🎯 Scope of Testing

### ✔️ In-Scope
* **Authentication Functional Testing:** Valid and invalid credential combinations.
* **Input Validation & UI Behavior:** Handling of blank fields, special characters, and inline error messaging.
* **Security & Edge Cases:** Brute-force account lockout mechanisms and session management.
* **Password Recovery Workflow:** "Forgot Password" routing and post-reset authentication.
* **Cross-Browser Compatibility:** Execution across modern desktop browsers.

### ❌ Out-of-Scope
* Internal HR dashboard administrative modules (Employee Management, Payroll, Leave tracking).
* Backend database schema validation and automated performance/load testing.

---

## 🛠️ Test Approach & Methodology
1. **Requirement Analysis:** Deconstructed system authentication workflows to establish baseline expected behaviors (REQ-01 through REQ-05).
2. **Decision Table Testing:** Designed a mathematical 2-input/3-state decision table covering all 9 permutation possibilities for Username and Password fields to guarantee 100% boundary and equivalence coverage.
3. **Execution & Defect Tracking:** Executed manual black-box tests across environments. Defects were logged with precise reproduction steps, severity/priority matrices, and root-cause notes.
4. **Traceability:** Established a Requirements Traceability Matrix (RTM) mapping every business requirement directly to test scenarios, test cases, and logged bug IDs.

---

## 💻 Test Environment
* **Primary Operating System:** Windows 11 (64-bit)
* **Browsers Tested:** 
  * Google Chrome (v150.0 / Latest Stable)
  * Microsoft Edge (Latest Stable)
* **Test Tooling:** Excel / Spreadsheet Management, PDF Documentation, GitHub Version Control.

---

## 📊 Key Findings & Defect Summary
During test execution, **4 primary defects** were identified and logged:

| Bug ID | Severity | Priority | Summary | Root Cause Analysis |
| :--- | :---: | :---: | :--- | :--- |
| **OHRM-101** | 🔴 Critical | **P1 - Urgent** | Login fails after password reset | Hash mismatch between reset module and auth table. |
| **OHRM-102** | 🔴 Critical | **P1 - Urgent** | Forgot Password returns HTTP 500 | Unhandled SMTP mail server timeout exception. |
| **OHRM-103** | 🟠 High | **P1 - Urgent** | Account lockout threshold ignored | Rate-limiting middleware missing on `/auth/login` API. |
| **OHRM-104** | 🟡 Medium | **P3 - Normal** | Missing inline validation on empty forms | Missing HTML5/JS client-side form validation attributes. |

---



## 📸 Test Execution Screenshots

### 1. Initial Login Page Interface
![Login Page](https://annis18.github.io/OrangeHRM_manual_test_suite/01_Login_Page.png)

*Caption: Baseline UI verification of the OrangeHRM authentication portal.*

### 2. Successful Authentication (TC_01)
![Valid Login](https://annis18.github.io/OrangeHRM_manual_test_suite/02_Valid_Login.png)

*Caption: Successful authentication and redirection to the employee Dashboard.*

### 3. Invalid Credentials Validation (TC_02 - TC_04)
![Invalid Credentials](https://annis18.github.io/OrangeHRM_manual_test_suite/03_Invalid_Credentials.png)

*Caption: System displaying the standard "Invalid credentials" callout box upon incorrect login attempts.*

### 4. Blank Password Validation (TC_05)
![Blank Password](https://annis18.github.io/OrangeHRM_manual_test_suite/04_Blank_Password.png)

*Caption: Inline "Required" error message triggered when submitting a valid username with an empty password.*

### 5. Blank Username Validation (TC_06)
![Blank Username](https://annis18.github.io/OrangeHRM_manual_test_suite/05_Blank_Username.png)

*Caption: Inline "Required" error message triggered when submitting a valid password with an empty username.*

### 6. Both Fields Blank Validation (TC_09)
![Both Fields Blank](https://annis18.github.io/OrangeHRM_manual_test_suite/06_Both_Fields_Blank.png)

*Caption: Inline "Required" error messages triggered when submitting the login form with both input fields empty.*

## 📁 Repository Structure

```text
📦 OrangeHRM_manual_test_suite
 ┣ 📜 01_Login_Page.png            # Screenshot: Baseline login page UI
 ┣ 📜 02_Valid_Login.png           # Screenshot: Dashboard redirection on valid login
 ┣ 📜 03_Invalid_Credentials.png   # Screenshot: Error callout for invalid credentials
 ┣ 📜 04_Blank_Password.png        # Screenshot: Inline error for blank password
 ┣ 📜 05_Blank_Username.png        # Screenshot: Inline error for blank username
 ┣ 📜 06_Both_Fields_Blank.png     # Screenshot: Inline errors for both fields blank
 ┣ 📜 O-hrm-TS.xlsx                # Complete spreadsheets (DT, TS, TC, BR, RTM)
 ┣ 📜 OrangeHRM_Test_Suite.pdf     # PDF Export for instant browser preview
 ┗ 📜 README.md                    # Project documentation & summary
