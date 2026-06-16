# Privacy Impact & Data Handling Risk Assessment  Customer-Facing Reservation Platform

## A PIA-style privacy assessment package aligned with Canadian privacy principles for a sanitized customer-facing reservation and payment application.

---

## 1. Project Overview

This repository presents a privacy-specific assessment package for a sanitized customer-facing reservation and payment-related web application.

The purpose of this project is to review how personal information is collected, used, stored, accessed, shared, protected, retained, and documented across key application workflows.

The project is structured as a PIA-style privacy assessment and data handling risk review. It is designed to demonstrate practical privacy analysis, personal information lifecycle mapping, privacy safeguards review, third-party processing assessment, risk documentation, and remediation tracking.

This project is intended for portfolio use in Canadian Privacy Analyst, Technical Privacy Analyst, Privacy Compliance Analyst, Privacy & Risk Analyst, Data Governance Analyst, Information Governance Analyst, and PIA Support Analyst roles.

---

## 2. Project Purpose

The purpose of this project is to answer the following practical privacy questions:

* What personal information is collected?
* Why is each data element collected?
* Where is personal information stored?
* Who can access it?
* Is access limited based on role and need-to-know?
* Is personal information shared with or processed by a third party?
* What safeguards protect the information?
* Are retention and deletion expectations documented?
* Are privacy risks documented and tracked?
* Are remediation actions assigned, prioritized, and supported by evidence?

This project focuses on practical privacy documentation rather than theoretical privacy commentary.

---

## 3. System Context

The assessment is based on a sanitized customer-facing reservation and payment-related application.

The assumed application environment includes:

* Customer-facing web interface
* Backend/API logic
* Application database
* Payment processing dependency
* Email/contact workflow
* Media or cloud service dependency
* Version control and deployment workflow
* Limited application/system logging

The workflows reviewed in this project include:

1. Reservation workflow
2. Contact form workflow
3. Checkout/payment-related workflow
4. Admin/internal access workflow
5. Third-party payment processing workflow
6. Hosting/cloud/vendor dependency workflow

---

## 4. Relationship to Existing ITGC / SOC 2 / GRC Projects

This privacy project is connected to, but separate from, prior ITGC, SOC 2 readiness, and enterprise GRC portfolio work.

The prior projects focused on control and audit questions such as:

* What controls exist?
* Which controls are missing or weak?
* Is audit evidence available?
* Are access, logging, change management, vendor, and security controls designed effectively?
* Are control gaps documented and tracked?

This project applies a privacy-specific lens to selected system and control observations.

The key privacy question is:

> What do these system and control observations mean for personal information protection, privacy safeguards, accountability, third-party processing, retention, breach readiness, and remediation under Canadian privacy principles?

This distinction is intentional.

A security or IT control issue is not automatically a privacy issue. It becomes privacy-relevant when it affects personal information handling, access, protection, retention, disclosure, accountability, or incident investigation.

---

## 5. Privacy-Relevant Translation of Technical Findings

| Technical / GRC Observation                     | Privacy-Relevant Interpretation                                  |
| ----------------------------------------------- | ---------------------------------------------------------------- |
| Lack of authentication controls                 | Accountability and access limitation risk                        |
| Absence of RBAC                                 | Need-to-know and privacy safeguards gap                          |
| Excessive privileged access                     | Unauthorized access and internal misuse risk                     |
| Inconsistent encryption of personal information | Safeguards deficiency                                            |
| Weak secrets management                         | Safeguards and breach readiness risk                             |
| Lack of change management controls              | Change governance risk for systems handling personal information |
| Insufficient logging and monitoring             | Accountability and incident investigation weakness               |
| Lack of third-party risk management             | Third-party processing and accountability gap                    |
| Incomplete retention documentation              | Limiting use, disclosure, and retention issue                    |

---

## 6. Canadian Privacy Framework Alignment

This project uses Canadian privacy principles as an assessment framework.

The primary framework used is:

* PIPEDA Fair Information Principles

The assessment maps privacy findings to the following principles:

1. Accountability
2. Identifying Purposes
3. Consent
4. Limiting Collection
5. Limiting Use, Disclosure, and Retention
6. Accuracy
7. Safeguards
8. Openness
9. Individual Access
10. Challenging Compliance

The project also reflects privacy management program concepts such as:

* Privacy roles and responsibilities
* Documented policies and procedures
* Risk assessment process
* Breach and incident response considerations
* Third-party/vendor management considerations
* Monitoring and remediation tracking
* Accountability documentation

This framework alignment is used for assessment structure and portfolio demonstration only.

This project does not claim that the application is compliant with PIPEDA or any other privacy law.

---

## 7. Jurisdictional Note

PIPEDA is used as the primary private-sector privacy framework for this portfolio assessment.

Depending on the actual organization, location of operations, individuals affected, and collection/use/disclosure context, other Canadian private-sector privacy laws may also be relevant, including Alberta PIPA, BC PIPA, and Québec private-sector privacy law.

Québec Law 25 is referenced only as general awareness where relevant. This project does not claim Québec Law 25 compliance.

Health-sector and public-sector privacy laws such as PHIPA, FIPPA, MFIPPA, FOIPOP, ATIA, or similar statutes are not treated as directly applicable unless the scenario specifically involves health information, public-sector institutions, or a defined statutory context.

---

## 8. In Scope

The project covers the following areas:

* Personal information inventory
* Data flow review
* Collection, use, storage, access, sharing, retention, and deletion analysis
* Third-party processing assessment
* Privacy safeguards review
* Access governance review
* Encryption coverage review
* Logging and accountability review
* Retention and deletion considerations
* Privacy issue documentation
* Privacy risk register
* Remediation tracker
* Evidence index
* Canadian privacy framework mapping
* Executive summary

---

## 9. Out of Scope

The following items are outside the scope of this project:

* Full penetration testing
* Network security assessment
* Source code security review
* Formal legal opinion
* Official Privacy Impact Assessment submission
* Regulatory audit
* Certification of compliance
* Full privacy program implementation
* Full data subject request program implementation
* Full breach response program implementation
* Formal vendor audit of Stripe or other third-party providers
* Use of real customer personal information
* Use of confidential production evidence
* PHIPA compliance assessment
* FIPPA, MFIPPA, FOIPOP, or public-sector privacy law compliance assessment
* Québec Law 25 compliance assessment
* Claims of hands-on enterprise privacy platform experience

---

## 10. Sanitization Disclaimer

This repository uses sanitized, anonymized, or mock information.

No real customer personal information, credentials, secrets, confidential business data, production screenshots, or proprietary evidence are included.

Any workflow diagrams, evidence references, data examples, and assessment notes are used only to demonstrate privacy assessment methodology and documentation structure.

---

## 11. Personal Information Elements Reviewed

The assessment considers the following personal information or privacy-relevant data elements:

* Name
* Email address
* Phone number
* Address
* Company name, if applicable
* Reservation details
* Contact message content
* Payment status
* Stripe transaction or payment reference
* Admin/internal user identifiers, if applicable
* System logs or access records, if applicable
* IP/device/session information, only where relevant and clearly marked as assumed or system-generated

For each data element, the assessment considers:

* What is collected
* Why it is collected
* Where it is stored
* Who can access it
* Whether it is shared with or processed by a third party
* What safeguards apply
* What retention or deletion consideration exists
* Which Canadian privacy principle is relevant
* What evidence supports the assessment

---

## 12. Key Privacy Themes

### 12.1 Personal Information Lifecycle

The project reviews personal information across collection, use, storage, access, sharing, retention, deletion, and evidence tracking.

### 12.2 Accountability

The assessment evaluates whether privacy-relevant decisions, ownership, evidence, findings, risks, and remediation actions are documented.

### 12.3 Safeguards

The project reviews whether personal information is protected through reasonable safeguards such as authentication, access control, encryption coverage, secrets management, and logging.

### 12.4 Access Limitation

The assessment considers whether internal access to personal information is limited based on role, operational purpose, and need-to-know.

### 12.5 Third-Party Processing

The project reviews the payment processing dependency and documents what data is processed externally versus what remains in the internal application environment.

### 12.6 Retention and Deletion

The assessment documents whether retention periods, deletion triggers, and disposal expectations are clearly defined.

### 12.7 Breach and Incident Readiness

The project includes breach triage considerations such as affected personal information category, safeguards involved, containment action, remediation action, and real risk of significant harm awareness.

---

## 13. Main Privacy Findings Summary

| Finding ID | Finding Title                                 | Privacy Theme     | Summary                                                                                                                                 |
| ---------- | --------------------------------------------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| PF-001     | Inconsistent Field-Level Protection           | Safeguards        | Selected customer contact fields may have stronger protection, while other identifiable customer fields may remain stored in plaintext. |
| PF-002     | RBAC / Access Limitation Gap                  | Access Governance | Admin or internal users may have broader access to personal information than necessary for their role.                                  |
| PF-003     | Limited Audit Logging                         | Accountability    | Limited visibility may exist into who accessed, modified, exported, or deleted personal information.                                    |
| PF-004     | Stripe Third-Party Processing Dependency      | Vendor Processing | Payment processing is handled externally, but documentation should clarify what payment-related data is retained internally.            |
| PF-005     | Retention / Deletion Documentation Incomplete | Retention         | Retention periods and deletion triggers may not be fully documented for reservation records, contact messages, and payment references.  |
| PF-006     | Evidence Traceability Gap                     | Accountability    | Privacy findings, evidence references, and remediation actions may not be centralized in a single privacy evidence index.               |
| PF-007     | Change Management Risk for PI Systems         | Governance        | Changes affecting systems that process personal information may be deployed without documented privacy or safeguard review.             |

---

## 14. Deliverables

| #  | Deliverable                                | Purpose                                                                                                                        |
| -- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| 1  | README.md                                  | Project overview, privacy positioning, scope, framework alignment, and artifact index                                          |
| 2  | 01_Project_Charter.md                      | Project objective, background, problem statement, scope, assumptions, methodology, success criteria, and limitations           |
| 3  | 02_System_Context_and_Assumptions.md       | System overview, workflows, data elements, components, third-party dependencies, assumptions, and limitations                  |
| 4  | 03_Personal_Information_Inventory.xlsx     | Inventory of personal information elements, purposes, storage, access, sharing, safeguards, retention, and evidence references |
| 5  | 04_Data_Flow_Map.md                        | Text-based and diagram-based mapping of personal information flows across key workflows                                        |
| 6  | 05_PIA_Style_Privacy_Assessment.md         | Structured PIA-style privacy assessment report                                                                                 |
| 7  | 06_Canadian_Privacy_Framework_Mapping.xlsx | Mapping of findings to Canadian privacy principles                                                                             |
| 8  | 07_Privacy_Safeguards_Gap_Log.xlsx         | Privacy safeguards gaps, impacts, recommendations, owners, target dates, and status                                            |
| 9  | 08_Vendor_Processing_Assessment_Stripe.md  | Third-party processing assessment for payment dependency                                                                       |
| 10 | 09_Privacy_Risk_Register.xlsx              | Privacy risk statements, ratings, mitigation actions, residual risks, and evidence references                                  |
| 11 | 10_Remediation_Tracker.xlsx                | Remediation actions, priority, owner, evidence required, closure criteria, and follow-up status                                |
| 12 | 11_Evidence_Index.xlsx                     | Centralized evidence traceability index                                                                                        |
| 13 | 12_Executive_Summary.md                    | Business-level summary of scope, top risks, recommendations, residual risk, and next steps                                     |

---

## 15. What This Project Demonstrates

This project demonstrates working knowledge of:

* Personal information inventory development
* Privacy data flow analysis
* PIA-style assessment structure
* Canadian privacy principles alignment
* Privacy safeguards review
* Access governance review
* Vendor processing documentation
* Retention and deletion analysis
* Privacy risk register development
* Remediation tracking
* Evidence indexing
* Translating technical control gaps into privacy-relevant risk language
* Preparing interview-defensible privacy documentation

---

## 16. What This Project Does Not Claim

This project does not claim that:

* The system is PIPEDA compliant
* The system is compliant with any privacy law
* A formal legal opinion was provided
* An official Privacy Impact Assessment was submitted
* A regulatory audit was conducted
* A certification of compliance was issued
* A full privacy program was implemented
* A data subject request program was formally managed
* A breach response program was formally managed
* A full third-party audit of Stripe or other vendors was performed
* Real customer data was used
* Confidential business evidence is included
* PHIPA, FIPPA, MFIPPA, FOIPOP, or public-sector privacy law compliance was assessed
* Québec Law 25 compliance was assessed
* Enterprise privacy tools such as OneTrust, BigID, Cyera, or Ketch were used hands-on
* CIPP/C certification has been completed



---

## 17. Disclaimer

This repository is a portfolio project prepared for educational and professional demonstration purposes.

It is not a formal legal opinion, official Privacy Impact Assessment, regulatory submission, certification, regulatory audit, or compliance attestation.

The analysis is based on sanitized assumptions, mock evidence references, and privacy-relevant interpretation of selected system and control observations.
