# NETWORKWALKS-TUMILARAEMMANUEL-B083-WK4-FINAL-PROJECT
# 🛡️ Healthcare Web Application Security Assessment

![Cybersecurity](https://img.shields.io/badge/Focus-Web%20Application%20Security-red)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Assessment](https://img.shields.io/badge/Assessment-Penetration%20Testing-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **A practical web application security assessment covering reconnaissance, authentication testing, PDF security, password analysis, metadata analysis, directory exposure, backup exposure, and sensitive-data security.**

---

## 📌 Project Overview

This project documents a structured security assessment of a healthcare web application performed in an authorized testing/learning environment.

The assessment followed a penetration-testing workflow beginning with reconnaissance and progressing through application enumeration, authentication testing, document security analysis, password-strength assessment, metadata analysis, web-directory discovery, backup exposure, and sensitive-data assessment.

The primary objective was to understand how weaknesses at different layers of a web application can combine to create security risks.

### Main Areas Assessed

* Domain reconnaissance
* Web technology identification
* Authentication
* Access control
* Laboratory report security
* PDF password protection
* Password-strength assessment
* Offline password analysis
* PDF metadata
* Web-directory exposure
* Database backup exposure
* Sensitive-data exposure
* Evidence handling
* Security remediation

---

# 🎯 Objectives

The assessment was conducted to:

1. Identify publicly exposed information.
2. Identify technologies used by the application.
3. Examine authentication functionality.
4. Assess access to protected laboratory reports.
5. Evaluate PDF password protection.
6. Assess the strength of document passwords.
7. Examine PDF metadata.
8. Identify exposed directories and backup files.
9. Assess the potential impact of exposed sensitive information.
10. Document security findings and recommended remediation.

---

# 🧪 Assessment Methodology

The assessment followed this workflow:

```text
Reconnaissance
      ↓
Technology Identification
      ↓
Application Enumeration
      ↓
Authentication Assessment
      ↓
Laboratory Report Assessment
      ↓
PDF Security Assessment
      ↓
Password Analysis
      ↓
PDF Decryption Validation
      ↓
Metadata Analysis
      ↓
Directory Enumeration
      ↓
Backup Exposure Assessment
      ↓
Sensitive Data Assessment
      ↓
Evidence Collection
      ↓
Risk Assessment
      ↓
Remediation
```

---

# 🛠️ Tools Used

| Tool / Technology        | Purpose                      |
| ------------------------ | ---------------------------- |
| Kali Linux               | Security testing environment |
| WHOIS                    | Domain information gathering |
| Web fingerprinting tools | Technology identification    |
| Web browser              | Application assessment       |
| PDF analysis tools       | PDF security analysis        |
| Password-analysis tools  | Password-strength assessment |
| Wordlists                | Authorized password testing  |
| qpdf                     | PDF processing               |
| Metadata tools           | Document metadata analysis   |
| GitHub                   | Project documentation        |

> Replace or update the tools above with the exact tools used during your assessment.

---

# 🔎 Phase 1 — Reconnaissance

## Objective

The first stage was to gather publicly available information about the target domain and understand its external footprint.

### Activities

* Domain information gathering
* DNS/infrastructure observation
* Web-service identification
* Server information gathering
* Technology identification

### Information Identified

The assessment identified information relating to:

* Domain infrastructure
* Web-server technology
* HTTPS configuration
* HTTP responses
* Application technologies

### Screenshot

![Reconnaissance](images/01-reconnaissance.png)

> **Screenshot 01 — Reconnaissance Results**

---

# 🌐 Phase 2 — Web Technology Identification

## Objective

The web application was examined to identify the technologies and server characteristics exposed by the application.

### Observations

The assessment identified:

* HTTPS implementation
* HTTP-to-HTTPS redirection
* Web-server technology
* HTTP response behavior
* Security-related headers

A `403 Forbidden` response was also observed for certain requests.

### Security Relevance

Technology information can assist further security assessment and may expose unnecessary information about the application's infrastructure.

### Screenshot

![Web Technology](images/02-web-technology.png)

> **Screenshot 02 — Web Technology Identification**

---

# 🔐 Phase 3 — Authentication Assessment

## Objective

The application's authentication mechanism was assessed to understand how it handled login attempts and access to authenticated functionality.

### Tested Areas

* Username/password authentication
* Authentication responses
* Login behavior
* Access to authenticated functionality
* Error handling

An unsuccessful authentication attempt returned an incorrect-password response.

### Security Controls to Consider

* Password complexity
* Account lockout
* Rate limiting
* MFA
* Session management
* Authentication logging
* Credential protection

### Screenshot

![Authentication](images/03-authentication.png)

> **Screenshot 03 — Authentication Testing**

---

# 🧪 Phase 4 — Laboratory Report Access

## Objective

After authentication, the available laboratory-report functionality was assessed.

The application provided access to downloadable laboratory reports in PDF format.

### Security Concern

Laboratory reports may contain highly sensitive healthcare information and therefore require strong:

* Authentication
* Authorization
* Encryption
* Access controls
* Logging
* Data-retention controls

### Screenshot

![Laboratory Reports](images/04-laboratory-reports.png)

> **Screenshot 04 — Laboratory Reports**

---

# 📄 Phase 5 — PDF Security Assessment

## Objective

The downloaded reports were examined to determine whether the documents had additional protection.

The PDFs were password protected.

The security model was therefore:

```text
Web Authentication
        ↓
Patient Portal
        ↓
Laboratory Report
        ↓
Password-Protected PDF
```

### Security Question

The assessment evaluated whether the PDF passwords provided an effective additional security control.

### Screenshot

![Protected PDF](images/05-protected-pdf.png)

> **Screenshot 05 — Password-Protected PDF**

---

# 🔑 Phase 6 — PDF Password Analysis

## Objective

The strength of the passwords protecting the PDF documents was assessed using an authorized password-analysis process.

### General Workflow

```text
Protected PDF
      ↓
Identify PDF security information
      ↓
Prepare authorized test data
      ↓
Password candidates
      ↓
Offline analysis
      ↓
Validate candidate
      ↓
Document access
```

### Key Observation

The assessment demonstrated that weak or predictable passwords can reduce the effectiveness of encrypted PDF documents.

### Security Lesson

Encryption protects the document, but the password protecting that encryption must also be sufficiently strong.

### Screenshot

![PDF Password Analysis](images/06-pdf-password-assessment.png)

> **Screenshot 06 — PDF Password Assessment**

---

# ✅ Phase 7 — Password Validation

A recovered password candidate was validated against the protected document within the authorized assessment.

Successful validation demonstrated that the document protection could be defeated when an insufficiently strong password was used.

### Screenshot

![Password Validation](images/07-password-validation.png)

> **Screenshot 07 — Password Validation**

> ⚠️ **Do not publish actual passwords, patient information, credentials, tokens, or other sensitive information in this repository.**

---

# 💻 Phase 8 — Offline Security Analysis

The assessment demonstrated offline analysis of a protected PDF.

The general process was:

```text
Protected PDF
      ↓
Extract required security representation
      ↓
Prepare local analysis data
      ↓
Use authorized password candidates
      ↓
Perform offline analysis
      ↓
Validate result
```

### Why This Matters

An online password attack interacts with the application:

```text
Tester → Web Application → Login Attempt
```

An offline attack works against an authorized copy of the protected artifact:

```text
Protected File
      ↓
Local Analysis
```

Once a protected file is obtained, application-level login protections such as rate limiting may no longer protect the document from offline password analysis.

### Screenshot

![Offline Analysis](images/08-offline-analysis.png)

> **Screenshot 08 — Offline Password Analysis**

---

# 🔓 Phase 9 — PDF Decryption Validation

After successful password validation, the PDF was processed to verify that the document could be opened and examined.

### Validation Checks

* File opened successfully.
* Document contents remained intact.
* Original evidence was preserved.
* Metadata could be examined.

### Screenshot

![Decrypted PDF](images/09-decrypted-pdf.png)

> **Screenshot 09 — Decrypted PDF**

---

# 🧾 Phase 10 — PDF Metadata Analysis

## Objective

The PDF metadata was examined for information that could disclose details about the document or its creation environment.

### Potential Metadata

PDF metadata may contain:

* Author
* Creator
* Producer
* Title
* Subject
* Creation date
* Modification date
* Software information
* File properties

### Security Impact

Metadata can unintentionally reveal information about:

* Software
* Internal processes
* Document-generation systems
* Organizational workflows
* File history

### Screenshot

![PDF Metadata](images/10-pdf-metadata.png)

> **Screenshot 10 — PDF Metadata**

---

# 📁 Phase 11 — Exposed `/old/` Directory

During further examination of the web application, an `/old/` directory was identified.

The directory exposed older application-related resources.

### Security Concern

Old directories can contain:

* Backup files
* Configuration files
* Previous application versions
* Temporary files
* Sensitive documents
* Database backups

### Risk

Leaving obsolete directories publicly accessible increases the application's attack surface.

### Screenshot

![Exposed Directory](images/11-old-directory.png)

> **Screenshot 11 — Exposed `/old/` Directory**

---

# 🗄️ Phase 12 — Database Backup Exposure

A database backup was identified within the exposed directory.

### Security Impact

A publicly accessible database backup may expose large quantities of application information, depending on its contents.

Potentially exposed information could include:

* User records
* Staff records
* Application configuration
* Account information
* Sensitive personal information
* Password-related information

### Recommended Action

Database backups should:

* Never be stored inside the public web root.
* Require authentication and authorization.
* Be encrypted.
* Be stored in dedicated backup infrastructure.
* Be monitored.
* Follow appropriate retention policies.

### Screenshot

![Database Backup](images/12-database-backup.png)

> **Screenshot 12 — Database Backup Exposure**

---

# 🔍 Phase 13 — Sensitive Data Exposure

The exposed material was reviewed to determine the potential sensitivity of information accessible through the identified weakness.

### Potential Impact

Sensitive information exposure may result in:

* Privacy violations
* Identity-related risks
* Credential compromise
* Phishing opportunities
* Unauthorized access
* Regulatory consequences
* Reputational damage

### Data-Minimization Approach

Only the minimum information required to demonstrate the vulnerability should be accessed.

Actual personal information should be:

* Redacted
* Anonymized
* Replaced with synthetic data
* Excluded from public repositories

### Screenshot

![Redacted Data Exposure](images/13-data-exposure-redacted.png)

> **Screenshot 13 — Redacted Data Exposure**

---

# 🔐 Phase 14 — Credential Handling

Any credentials discovered during an authorized assessment must be treated as sensitive security evidence.

### Secure Handling

Credentials should:

* Never be published publicly.
* Never be included in GitHub screenshots.
* Be stored securely.
* Be encrypted where appropriate.
* Be accessible only to authorized personnel.
* Be rotated or revoked where necessary.
* Be securely deleted after the assessment when no longer required.

### Screenshot

![Redacted Credentials](images/14-redacted-credentials.png)

> **Screenshot 14 — Redacted Credential Evidence**

---

# 📊 Phase 15 — Data Analysis

The final stage involved organizing assessment data into a structured format for analysis.

For a professional assessment, sensitive information should be minimized and redacted.

### Example

| ID        | Role     | Department | Sensitive Information |
| --------- | -------- | ---------- | --------------------- |
| STAFF-001 | Redacted | Redacted   | `[REDACTED]`          |
| STAFF-002 | Redacted | Redacted   | `[REDACTED]`          |
| STAFF-003 | Redacted | Redacted   | `[REDACTED]`          |

### Screenshot

![Data Analysis](images/15-data-analysis.png)

> **Screenshot 15 — Data Analysis**

---

# 🚨 Security Findings

| ID   | Finding                           | Category                | Risk       |
| ---- | --------------------------------- | ----------------------- | ---------- |
| F-01 | Information disclosure            | Information Disclosure  | Medium     |
| F-02 | Weak PDF passwords                | Password Security       | High       |
| F-03 | Sensitive document exposure       | Data Protection         | High       |
| F-04 | Exposed `/old/` directory         | Misconfiguration        | High       |
| F-05 | Public database backup            | Sensitive Data Exposure | Critical   |
| F-06 | PDF metadata disclosure           | Information Disclosure  | Low/Medium |
| F-07 | Excessive sensitive-data exposure | Data Security           | High       |
| F-08 | Insecure sensitive-data handling  | Data Governance         | High       |

> Risk classifications should be adjusted according to the organization's approved risk methodology and the actual assessment environment.

---

# 🛠️ Remediation Recommendations

## 1. Secure Database Backups

* Remove backups from the public web root.
* Store backups in dedicated storage.
* Encrypt backup files.
* Restrict access.
* Monitor backup access.
* Review backup retention.

## 2. Strengthen PDF Passwords

* Use long, random passwords.
* Avoid predictable information.
* Avoid password reuse.
* Use modern encryption.
* Consider centralized document-access controls.

## 3. Secure Authentication

* Enforce strong passwords.
* Implement MFA where appropriate.
* Apply rate limiting.
* Implement account lockout controls.
* Monitor authentication events.
* Secure session management.

## 4. Improve Authorization

* Implement least privilege.
* Apply server-side authorization.
* Verify access to every sensitive document.
* Conduct regular access reviews.

## 5. Remove Exposed Files

* Remove obsolete directories.
* Remove temporary files.
* Remove backup files from public locations.
* Disable unnecessary directory listing.

## 6. Protect Sensitive Information

* Encrypt sensitive information.
* Minimize collected data.
* Restrict access.
* Monitor access.
* Apply appropriate retention and disposal policies.

## 7. Review Document Metadata

* Remove unnecessary metadata.
* Review documents before external distribution.
* Implement document sanitization procedures.

---

# 📋 Attack Chain Summary

The assessment can be summarized as:

```text
Reconnaissance
      ↓
Web Technology Identification
      ↓
Authentication Assessment
      ↓
Laboratory Report Access
      ↓
Protected PDF Discovery
      ↓
Password Security Assessment
      ↓
Password Validation
      ↓
PDF Analysis
      ↓
Metadata Analysis
      ↓
Directory Discovery
      ↓
Database Backup Exposure
      ↓
Sensitive Data Assessment
      ↓
Evidence Collection
      ↓
Risk Assessment
      ↓
Remediation
```

---

# 🧠 Key Lessons Learned

### 1. Authentication alone is not enough

A secure login mechanism does not automatically secure every resource behind the application.

### 2. Strong encryption requires strong passwords

Encrypted files can still be vulnerable when weak passwords are used.

### 3. Backups are high-value assets

A database backup can contain large amounts of sensitive information and must be protected accordingly.

### 4. Old files increase attack surface

Unused directories and obsolete files should be removed.

### 5. Metadata can disclose information

Documents may contain information that users do not realize is embedded in them.

### 6. Sensitive data should be minimized

A penetration tester should access only the amount of sensitive information necessary to prove a vulnerability.

### 7. Security evidence must also be protected

Testing activities can create additional privacy risks if evidence is stored or shared improperly.

---

# 📸 Screenshot Evidence

All screenshots used in this project should be appropriately redacted.

| #  | Evidence                | File                             |
| -- | ----------------------- | -------------------------------- |
| 01 | Reconnaissance          | `01-reconnaissance.png`          |
| 02 | Web Technology          | `02-web-technology.png`          |
| 03 | Authentication          | `03-authentication.png`          |
| 04 | Laboratory Reports      | `04-laboratory-reports.png`      |
| 05 | Protected PDF           | `05-protected-pdf.png`           |
| 06 | PDF Password Assessment | `06-pdf-password-assessment.png` |
| 07 | Password Validation     | `07-password-validation.png`     |
| 08 | Offline Analysis        | `08-offline-analysis.png`        |
| 09 | Decrypted PDF           | `09-decrypted-pdf.png`           |
| 10 | PDF Metadata            | `10-pdf-metadata.png`            |
| 11 | Exposed Directory       | `11-old-directory.png`           |
| 12 | Database Backup         | `12-database-backup.png`         |
| 13 | Data Exposure           | `13-data-exposure-redacted.png`  |
| 14 | Credential Handling     | `14-redacted-credentials.png`    |
| 15 | Data Analysis           | `15-data-analysis.png`           |

---

# 📂 Recommended Repository Structure

```text
healthcare-web-security-assessment/
│
├── README.md
│
├── images/
│   ├── 01-reconnaissance.png
│   ├── 02-web-technology.png
│   ├── 03-authentication.png
│   ├── 04-laboratory-reports.png
│   ├── 05-protected-pdf.png
│   ├── 06-pdf-password-assessment.png
│   ├── 07-password-validation.png
│   ├── 08-offline-analysis.png
│   ├── 09-decrypted-pdf.png
│   ├── 10-pdf-metadata.png
│   ├── 11-old-directory.png
│   ├── 12-database-backup.png
│   ├── 13-data-exposure-redacted.png
│   ├── 14-redacted-credentials.png
│   └── 15-data-analysis.png
│
└── evidence/
    └── README.md
```

---

# 🎓 Skills Demonstrated

This project demonstrates practical exposure to:

* Web application security
* Penetration-testing methodology
* Reconnaissance
* Web technology fingerprinting
* Authentication assessment
* Access-control assessment
* PDF security
* Password security
* Offline password analysis
* Metadata analysis
* Directory enumeration
* Backup exposure assessment
* Sensitive-data assessment
* Evidence handling
* Risk identification
* Security documentation
* Remediation planning
* Data minimization

---

# 📚 Project Takeaway

This assessment demonstrates how several weaknesses can combine to increase the security impact of a web application.

The key security chain was:

```text
Weak/Exposed Security Control
          ↓
Sensitive Resource Discovery
          ↓
Additional Security Weakness
          ↓
Unauthorized Exposure Risk
          ↓
Sensitive Information Exposure
```

Effective security therefore requires a layered approach covering:

```text
Authentication
      +
Authorization
      +
Encryption
      +
Password Security
      +
Server Configuration
      +
Backup Security
      +
Data Protection
      +
Monitoring
      +
Secure Evidence Handling
```

---

# ⚠️ Responsible Use

This project is intended for:

* Cybersecurity education
* Authorized penetration testing
* Security research
* Laboratory environments
* Capture-the-Flag exercises
* Portfolio development

Do not test systems, applications, accounts, or networks without explicit authorization.

Do not publish:

* Real passwords
* API keys
* Session tokens
* Patient information
* Staff personal information
* Private database records
* Confidential documents

Use redacted or synthetic information when publishing cybersecurity projects.

---

# 👤 Author

**Name:** `YOUR NAME`

**Role:** `Cybersecurity Student / Ethical Hacking Trainee`

**GitHub:** `YOUR GITHUB URL`

**LinkedIn:** `YOUR LINKEDIN URL`

**Email:** `YOUR EMAIL`

---

# 📌 Project Status

**Assessment:** Completed
**Documentation:** Completed
**Evidence:** Redacted
**Remediation:** Recommended

---

> **Disclaimer:** This documentation is intended for authorized cybersecurity assessment and educational purposes. The techniques and findings should only be applied to systems where explicit permission has been granted.
