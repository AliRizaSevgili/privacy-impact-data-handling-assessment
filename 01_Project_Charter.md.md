# Project Charter

## Privacy Impact & Data Handling Risk Assessment: Customer-Facing Reservation Platform

## 1. Project Objective

The objective of this project is to create a privacy-specific assessment package for a sanitized customer-facing reservation and payment-related web application.

The assessment reviews how personal information is collected, used, stored, accessed, shared, protected, retained, and documented across key application workflows.

The project is structured as a PIA-style privacy assessment package aligned with Canadian privacy principles. It is intended to demonstrate practical privacy analysis, privacy risk documentation, data handling review, safeguards assessment, vendor processing review, and remediation tracking.

This project does not provide a formal legal opinion, official Privacy Impact Assessment submission, regulatory audit, or certification of compliance.

## 2. Background

A prior ITGC, SOC 2 readiness, and enterprise GRC portfolio context identified several technical and governance observations involving access control, encryption coverage, logging, vendor dependency, change management, and evidence traceability.

Those observations are relevant to privacy because the application processes customer personal information through reservation, contact, checkout/payment-related, and administrative workflows.

However, this project does not repeat the prior ITGC, SOC 2, or GRC assessment.

Instead, this project applies a privacy-specific lens to selected system and control observations.

The key question is:

> What do these system and control observations mean for personal information protection, accountability, safeguards, third-party processing, retention, breach readiness, and privacy remediation?

## 3. Problem Statement

The application context includes personal information such as customer name, email address, phone number, address, reservation details, contact message content, payment status, payment reference information, and internal user identifiers.

Selected technical and governance observations may create privacy-relevant risk if they affect:

* Access to personal information
* Protection of identifiable customer data
* Logging and investigation of personal information access
* Documentation of third-party processing
* Retention and deletion expectations
* Evidence traceability for privacy findings
* Remediation ownership and follow-up

The problem addressed by this project is the lack of a centralized privacy assessment package that documents:

* What personal information is involved
* Why it is collected
* Where it flows
* Who can access it
* Which third parties process it
* What safeguards apply
* What retention and deletion considerations exist
* What privacy risks were identified
* What remediation actions are recommended
* What evidence supports the assessment

## 4. Project Scope

### 4.1 In Scope

The project covers the following privacy assessment areas:

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
* Canadian privacy framework mapping
* Privacy risk register
* Remediation tracker
* Evidence index
* Executive summary

### 4.2 Workflows in Scope

The following workflows are included:

1. Reservation workflow
2. Contact form workflow
3. Checkout/payment-related workflow
4. Admin/internal access workflow
5. Third-party payment processing workflow
6. Hosting/cloud/vendor dependency workflow

### 4.3 Personal Information Elements in Scope

The following personal information or privacy-relevant data elements are considered:

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

## 5. Out of Scope

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
* Quebec Law 25 compliance assessment
* Claims of hands-on enterprise privacy platform experience

## 6. Stakeholders

The following stakeholder roles are assumed for assessment purposes:

| Stakeholder                | Role in Assessment                                                                                                   |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Business Owner             | Defines business purpose for reservation, contact, and payment-related workflows                                     |
| Application Owner          | Provides system context and application workflow information                                                         |
| Privacy Reviewer           | Reviews collection, use, storage, access, sharing, retention, and safeguards                                         |
| Security / IT Reviewer     | Provides technical control context related to access, encryption, logging, change management, and secrets management |
| Vendor / Third-Party Owner | Documents third-party processing dependency and vendor-related accountability considerations                         |
| Admin / Internal User      | Accesses reservation, contact, or payment-related records for operational purposes                                   |
| Customer / Individual      | Provides personal information through reservation, contact, or payment-related workflows                             |

## 7. Assumptions

This project is based on the following assumptions:

1. The application is a customer-facing reservation and payment-related platform.
2. The system collects personal information from customers through reservation and contact workflows.
3. Payment processing is handled by a third-party payment processor, such as Stripe.
4. The internal application may retain limited payment-related references, such as payment status or transaction reference.
5. The application database stores reservation and contact-related records.
6. Selected customer contact fields may have stronger protection than other identifiable customer fields.
7. Internal/admin users may have broader access than necessary in the absence of mature RBAC.
8. Logging may not fully capture access, modification, export, or deletion of personal information.
9. Retention periods and deletion triggers may not be fully documented.
10. Evidence references are sanitized and used only for portfolio demonstration purposes.
11. No real customer data, credentials, secrets, or confidential business evidence are included.

## 8. Methodology

The assessment follows a structured privacy review methodology.

### Step 1: Define System Context

Document the system overview, workflows, data elements, technical components, vendor dependencies, and assumptions.

### Step 2: Build Personal Information Inventory

Identify personal information elements and document:

* Collection point
* Purpose of collection
* Use
* Storage location
* Access role
* Third-party sharing
* Retention consideration
* Deletion trigger
* Consent consideration
* Relevant privacy principle
* Risk notes
* Evidence reference

### Step 3: Map Data Flows

Map how personal information moves through the application across:

* Reservation workflow
* Contact form workflow
* Checkout/payment-related workflow
* Admin/internal access workflow
* Third-party payment processing workflow
* Hosting/cloud/vendor dependency workflow

### Step 4: Assess Privacy Safeguards

Review privacy-relevant safeguards such as:

* Authentication
* RBAC / role-based access
* Need-to-know limitation
* Encryption coverage
* Secrets management
* Audit logging
* Monitoring
* Evidence traceability
* Retention and deletion controls

### Step 5: Review Third-Party Processing

Document payment processor dependency and distinguish between:

* Data processed by the third party
* Data retained internally
* Accountability considerations
* Safeguards considerations
* Contractual/documentation considerations
* Vendor-related risk observations

### Step 6: Map Findings to Canadian Privacy Principles

Map each finding to relevant Canadian privacy principles, especially:

* Accountability
* Identifying Purposes
* Consent
* Limiting Collection
* Limiting Use, Disclosure, and Retention
* Safeguards
* Openness
* Individual Access
* Challenging Compliance

### Step 7: Document Privacy Risks

Create privacy risk statements that identify:

* Cause
* Affected data element or workflow
* Privacy principle
* Impact
* Likelihood
* Risk rating
* Existing control
* Control gap
* Recommended mitigation
* Residual risk
* Evidence reference

### Step 8: Track Remediation

Document remediation actions with:

* Related risk or finding
* Recommended action
* Priority
* Owner
* Target date
* Evidence required
* Closure criteria
* Follow-up status

### Step 9: Prepare Executive Summary

Prepare a business-readable summary of:

* Assessment scope
* Top privacy risks
* Key Canadian privacy themes
* High-priority recommendations
* Residual risk
* Next steps
* Limitations

## 9. Canadian Privacy Framework Alignment

This project uses Canadian privacy principles as an assessment framework.

The primary framework is:

* PIPEDA Fair Information Principles

The project also reflects privacy management program concepts such as:

* Privacy roles and responsibilities
* Documented policies and procedures
* Training and awareness considerations
* Risk assessment process
* Breach and incident response considerations
* Third-party/vendor management considerations
* Monitoring and remediation tracking
* Accountability documentation

This project uses these frameworks for alignment and documentation structure only.

The project does not claim that the application is compliant with PIPEDA or any other privacy law.

## 10. Key Assessment Questions

The assessment is guided by the following questions:

1. What personal information is collected?
2. Why is each data element collected?
3. Is the collection limited to what is necessary for the identified purpose?
4. Where is personal information stored?
5. Who can access personal information?
6. Is access limited by role and need-to-know?
7. Is personal information shared with or processed by a third party?
8. What safeguards protect personal information?
9. Are safeguards appropriate to the sensitivity and use of the information?
10. Are retention periods and deletion triggers documented?
11. Is there sufficient logging to support accountability and incident investigation?
12. Are privacy findings supported by evidence references?
13. Are remediation actions documented, assigned, and tracked?
14. Are breach or privacy incident triage considerations addressed?
15. Are Canadian privacy principles reflected in the assessment?

## 11. Main Privacy Findings to Be Assessed

The project will assess the following privacy-relevant findings.

### PF-001: Inconsistent Field-Level Protection

Selected customer contact fields may have stronger protection, while other identifiable customer fields such as name, address, or company information may remain stored in plaintext.

Privacy relevance:

* Safeguards may not be consistently applied to identifiable customer data.

Relevant principles:

* Safeguards
* Accountability
* Limiting Use, Disclosure, and Retention

### PF-002: RBAC / Access Limitation Gap

Admin or internal users may have broader access to customer personal information than necessary.

Privacy relevance:

* Need-to-know and role-based access limitation may not be sufficiently enforced.

Relevant principles:

* Safeguards
* Accountability
* Limiting Use, Disclosure, and Retention

### PF-003: Limited Audit Logging

The system may have limited visibility into who accessed, modified, exported, or deleted personal information.

Privacy relevance:

* Incident investigation, accountability, and compliance challenge handling may be weakened.

Relevant principles:

* Accountability
* Safeguards
* Challenging Compliance

### PF-004: Stripe Third-Party Processing Dependency

Payment processing is handled externally, but internal documentation should clarify what payment-related data is processed by Stripe and what remains in the internal system.

Privacy relevance:

* Vendor reliance and third-party processing accountability should be documented.

Relevant principles:

* Accountability
* Safeguards
* Openness
* Limiting Use, Disclosure, and Retention

### PF-005: Retention / Deletion Documentation Incomplete

Retention periods and deletion triggers may not be fully documented for reservation records, contact messages, and payment-related references.

Privacy relevance:

* Personal information may be kept longer than necessary without clear business or legal justification.

Relevant principles:

* Limiting Use, Disclosure, and Retention
* Accountability
* Openness

### PF-006: Evidence Traceability Gap

Privacy findings, evidence references, and remediation actions may not be centralized.

Privacy relevance:

* Accountability and audit readiness may be weakened if findings cannot be traced to evidence and closure criteria.

Relevant principles:

* Accountability
* Challenging Compliance
* Safeguards

### PF-007: Change Management Risk for Systems Handling Personal Information

Changes affecting systems that process personal information may be deployed without documented approval or privacy-relevant review.

Privacy relevance:

* Untested or undocumented changes may affect safeguards, access controls, data handling, or retention behavior.

Relevant principles:

* Accountability
* Safeguards

## 12. Deliverables

The project will produce the following deliverables:

| #  | Deliverable                                | Purpose                                            |
| -- | ------------------------------------------ | -------------------------------------------------- |
| 1  | README.md                                  | Project overview and positioning                   |
| 2  | 01_Project_Charter.md                      | Project objective, scope, methodology, limitations |
| 3  | 02_System_Context_and_Assumptions.md       | System context and assumptions                     |
| 4  | 03_Personal_Information_Inventory.xlsx     | Data element inventory and lifecycle documentation |
| 5  | 04_Data_Flow_Map.md                        | Personal information flow mapping                  |
| 6  | 05_PIA_Style_Privacy_Assessment.md         | Structured privacy assessment report               |
| 7  | 06_Canadian_Privacy_Framework_Mapping.xlsx | Findings mapped to Canadian privacy principles     |
| 8  | 07_Privacy_Safeguards_Gap_Log.xlsx         | Privacy safeguards gaps and recommendations        |
| 9  | 08_Vendor_Processing_Assessment_Stripe.md  | Third-party processing assessment                  |
| 10 | 09_Privacy_Risk_Register.xlsx              | Privacy risk register                              |
| 11 | 10_Remediation_Tracker.xlsx                | Remediation action tracker                         |
| 12 | 11_Evidence_Index.xlsx                     | Evidence traceability index                        |
| 13 | 12_Executive_Summary.md                    | Business-level summary                             |

## 13. Success Criteria

This project will be considered successful if it produces a privacy-specific package that:

1. Clearly distinguishes privacy analysis from ITGC, SOC 2, and general GRC analysis.
2. Documents the personal information lifecycle across key workflows.
3. Identifies collection, use, storage, access, sharing, retention, and deletion considerations.
4. Maps privacy findings to Canadian privacy principles.
5. Converts selected technical/control observations into privacy-relevant risk language.
6. Includes a personal information inventory, data flow map, framework mapping, risk register, remediation tracker, and evidence index.
7. Uses sanitized evidence and avoids real customer data.
8. Avoids overclaiming compliance, certification, formal legal opinion, or official PIA work.
9. Produces artifacts that can be explained in a Privacy Analyst or Technical Privacy Analyst interview.

## 14. Limitations

This project has the following limitations:

* It is based on sanitized assumptions and portfolio evidence.
* It does not include real customer records.
* It does not include confidential system evidence.
* It does not validate all production configurations.
* It does not include a full source code review.
* It does not include a full vendor audit.
* It does not provide a formal legal opinion.
* It does not certify compliance with PIPEDA or any other privacy law.
* It does not represent an official Privacy Impact Assessment submitted to a regulator or public-sector institution.
* It does not claim direct application of health-sector or public-sector privacy laws unless the scenario specifically requires them.

## 15. Overclaim Control

The following language should be used:

* PIA-style privacy assessment
* Privacy-relevant data handling risk assessment
* Canadian privacy-principles-based review
* PIPEDA-aligned assessment structure
* Privacy safeguards review
* Personal information lifecycle review
* Third-party processing assessment
* Privacy remediation tracking
* Evidence-based privacy risk documentation

The following language should not be used:

* PIPEDA compliant
* Certified compliant
* Formal legal opinion
* Official PIA
* Led formal PIA
* Owned privacy program
* Implemented full privacy-by-design program
* Managed DSR program
* Conducted regulatory audit
* PHIPA compliance
* FIPPA compliance
* Law 25 compliance
* OneTrust hands-on experience
* BigID hands-on experience
* Cyera hands-on experience
* Ketch hands-on experience
* CIPP/C certified, unless certification is completed



## 16. Disclaimer

This project is a portfolio assessment created for professional demonstration and educational purposes.

It is not a formal legal opinion, official Privacy Impact Assessment, regulatory audit, certification, or compliance attestation.

All evidence references, examples, workflows, and data elements are sanitized, anonymized, or mock representations designed to demonstrate privacy assessment methodology.
