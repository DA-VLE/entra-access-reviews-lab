# 🔐 Microsoft Entra ID Access Reviews Lab

![Microsoft Entra ID](https://img.shields.io/badge/Microsoft%20Entra%20ID-IAM-blue)
![Identity Governance](https://img.shields.io/badge/Identity-Governance-success)
![Access Reviews](https://img.shields.io/badge/Access-Reviews-informational)
![PowerShell](https://img.shields.io/badge/PowerShell-Automation-5391FE?logo=powershell&logoColor=white)
![CSV](https://img.shields.io/badge/Export-CSV-orange)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

## Overview
This home lab demonstrates how to configure and execute an **Access Review** in **Microsoft Entra ID** to validate whether users should still retain access to a sensitive group.

Access Reviews are a core component of **Identity Governance**. They help organizations regularly verify access rights, reduce excessive privileges, and improve audit readiness by ensuring that users only keep the access they still need.

---

## Project Goal
The goal of this lab was to simulate a real-world **access recertification** scenario by:

- creating a review on a test group,
- assigning a reviewer,
- collecting review decisions (**Approve / Deny**),
- exporting the results and analyzing the output for governance purposes.

---

## Business Scenario
In many organizations, users may keep access longer than necessary after changing teams, completing a project, or no longer needing privileged permissions.

To address this risk, security and IAM teams regularly run **access reviews** to confirm whether access is still justified.

This lab reproduces that process in a simple Microsoft Entra environment by reviewing membership in a sensitive test group.

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Entra ID Governance
- Access Reviews
- Microsoft Entra Admin Center
- My Access
- CSV / Excel

---

## Lab Setup
This lab was built with a simple and controlled environment:

- **1 security group** used as the review target
- **4 test users** added as members
- **1 designated reviewer**
- **1 Access Review** configured for a short review cycle

---

## Project Steps

### 1. Environment Preparation
A test environment was prepared in Microsoft Entra ID:

- a security group was created,
- multiple test users were added,
- a reviewer was defined for the access review.

### 2. Access Review Configuration
An **Access Review** was created from the Entra portal using the **Resource review** template.

Main settings included:

- review target: **test group**
- review type: **one-time review**
- duration: **1 day**
- reviewer: **selected user** (the reviewer could be the superior, the manager or the user himself)
- justification required
- notifications and reminders enabled

### 3. Review Execution
The reviewer accessed the review and made decisions for each user:

- **Approve** to keep access
- **Deny** to remove access

This step highlighted an important governance concept: the review decision is made by the reviewer, while Microsoft Entra may also provide **recommendations** based on signals such as recent sign-in activity.

### 4. Results Export and Analysis
Once the review was completed, the results were exported in **CSV** format and imported into Excel for cleanup and analysis.

The exported data included:

- reviewed user name
- UPN
- decision outcome
- review date
- reason / justification
- reviewer identity
- applied by information

---

## Key Learning Outcomes
Through this lab, I learned how to:

- configure **Access Reviews** in Microsoft Entra ID,
- understand how **Approve / Deny** decisions support access governance,
- interpret review recommendations versus real business decisions,
- export and structure review data for audit or reporting purposes.

This project also reinforced the importance of **least privilege** and periodic access recertification in IAM programs.

---

## Results
This lab successfully demonstrated how Microsoft Entra ID can be used to support **access governance** workflows.

It provided practical insight into how organizations can:

- validate whether access is still justified,
- reduce overprivileged accounts,
- improve traceability of access decisions,
- support compliance and audit evidence collection.

---

## Security & Governance Value
This lab demonstrates several important IAM and governance concepts:

- **Access recertification**
- **Least privilege**
- **Identity Governance**
- **Manual review with justification**
- **Auditability of access decisions**
- **Reduction of excessive or stale access**

---

## Future Improvements
Possible next steps for this project include:

- reviewing **privileged roles** instead of only a test group,
- automating result extraction with **PowerShell + Microsoft Graph API**,
---

