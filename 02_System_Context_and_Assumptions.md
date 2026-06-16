# System Context and Assumptions

## Privacy Impact & Data Handling Risk Assessment: Customer-Facing Reservation Platform

## 1. Purpose of This Document

The purpose of this document is to define the system context, workflows, data elements, technical components, third-party dependencies, assumptions, evidence boundaries, and limitations used for this privacy assessment.

This document supports the later deliverables in this repository, including:

* Personal Information Inventory
* Data Flow Map
* PIA-style Privacy Assessment
* Canadian Privacy Framework Mapping
* Privacy Safeguards Gap Log
* Vendor Processing Assessment
* Privacy Risk Register
* Remediation Tracker
* Evidence Index

This document does not assess legal compliance. It establishes the working context for a privacy-relevant data handling review.

## 2. Assessment Context

This project reviews a sanitized customer-facing reservation and payment-related web application.

The application is assumed to support customers who want to book pottery classes, submit contact inquiries, and complete payment-related steps through an online workflow.

The assessment focuses on how personal information may be collected, used, stored, accessed, shared, protected, retained, and documented across the application lifecycle.

This project is based on sanitized assumptions, mock evidence references, and selected technical observations from related ITGC, SOC 2 readiness, and GRC portfolio work.

The privacy assessment applies a Canadian privacy-principles-based lens to those observations. It does not claim that the application is compliant with PIPEDA or any other privacy law.

## 3. System Overview

The assumed system is a customer-facing reservation and payment-related web application.

At a high level, the system includes:

* A public-facing website or web interface
* Reservation form or booking workflow
* Contact form workflow
* Checkout or payment-related workflow
* Backend/API logic
* Application database
* Admin or internal access interface
* Third-party payment processor
* Email service dependency
* Cloud or media storage dependency
* Hosting and deployment workflow
* Application or system logging with limited audit visibility

The system processes customer information for operational purposes such as booking management, customer communication, payment confirmation, and internal administrative follow-up.

## 4. Business Purpose

The assumed business purpose of the application is to support customer reservations and related operational activities.

The application may collect and process personal information for the following purposes:

* Creating and managing reservations
* Communicating with customers about bookings or inquiries
* Processing or confirming payment-related activity
* Supporting customer service and operational follow-up
* Maintaining records needed for business operations
* Supporting security, troubleshooting, and incident investigation where logs are available

The assessment does not assume that personal information is collected for unrelated marketing, profiling, analytics, or automated decision-making unless specifically stated in later documentation.

## 5. Workflows in Scope

The following workflows are included in the assessment.

### 5.1 Reservation Workflow

Customers submit reservation information through the web application.

Possible data elements include:

* Name
* Email address
* Phone number
* Reservation date and time
* Class or service selected
* Number of participants
* Customer notes, if applicable

Privacy relevance:

* This workflow involves direct collection of customer personal information.
* The purpose of collection should be clearly documented.
* Access to reservation records should be limited to users with an operational need.
* Retention and deletion expectations should be defined.

### 5.2 Contact Form Workflow

Customers submit inquiries through a contact form.

Possible data elements include:

* Name
* Email address
* Phone number, if provided
* Contact message content
* Company name, if applicable

Privacy relevance:

* Contact message content may contain unexpected personal information.
* The organization should avoid collecting unnecessary information.
* Internal access to contact messages should be limited.
* Retention expectations for inquiries should be documented.

### 5.3 Checkout and Payment-Related Workflow

Customers complete or initiate payment-related activity through a third-party payment processor.

Possible data elements include:

* Payment status
* Transaction or payment reference
* Customer email or payment-related identifier
* Reservation reference connected to payment status

Privacy relevance:

* Payment processing is handled externally.
* The internal system should document what payment-related information is retained internally.
* The assessment does not assume that full cardholder data is stored in the internal application.
* Vendor dependency and accountability considerations should be documented.

### 5.4 Admin and Internal Access Workflow

Internal users may access reservation, contact, and payment-related records for operational purposes.

Possible access roles include:

* Business owner
* Application owner
* Admin user
* Customer service or operations user
* Technical support user

Privacy relevance:

* Internal access should be limited by role and need-to-know.
* Excessive privileged access can create privacy risk.
* Audit logging should support accountability and investigation.
* Access review evidence should be documented where available.

### 5.5 Third-Party Payment Processing Workflow

The application relies on a third-party payment processor, assumed to be Stripe, for payment processing.

Possible data handled by the vendor may include:

* Payment information submitted through the payment workflow
* Payment status
* Transaction reference
* Customer payment-related identifiers

Privacy relevance:

* The organization remains accountable for documenting third-party processing expectations.
* The internal system should distinguish between data processed by Stripe and data retained internally.
* Contractual, security, privacy, and documentation considerations should be captured.
* This assessment does not include a formal audit of Stripe controls.

### 5.6 Hosting, Cloud, and Deployment Dependency Workflow

The application may rely on hosting, deployment, source control, email, or cloud/media services.

Possible dependencies include:

* Hosting or deployment provider
* Version control platform
* Email service
* Cloud or media storage service
* Application database provider or hosted database environment

Privacy relevance:

* Vendor dependencies may affect where personal information or related metadata is stored.
* Secrets management and deployment practices may affect safeguards.
* Change management can affect systems that process personal information.
* Evidence should distinguish confirmed facts from assumptions.

## 6. System Components

| Component                                       | Assumed Role                                                                    | Privacy Relevance                                               |
| ----------------------------------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Customer-facing web interface                   | Allows customers to submit reservations, inquiries, and payment-related actions | Primary collection point for personal information               |
| Backend/API logic                               | Processes reservation, contact, and payment-related requests                    | Determines how personal information is handled and routed       |
| Application database                            | Stores reservation, contact, and operational records                            | Key storage point for personal information                      |
| Admin/internal interface                        | Allows internal users to view or manage records                                 | Access governance and need-to-know concerns                     |
| Stripe or comparable payment processor          | Processes payment-related activity                                              | Third-party processing and accountability consideration         |
| Gmail SMTP or comparable email service          | Supports customer communication or notifications                                | Potential disclosure or transmission pathway                    |
| Cloudinary or comparable media/cloud dependency | Supports media or file-related service needs                                    | Vendor dependency, storage, and access consideration            |
| GitHub or comparable version control platform   | Supports source control and deployment workflow                                 | Change governance and secrets management consideration          |
| Hosting/deployment environment                  | Hosts the customer-facing application                                           | Security, availability, and environment configuration relevance |
| Application/system logs                         | Records selected system or user activity                                        | Accountability, investigation, and breach triage relevance      |

## 7. Personal Information Elements Considered

The following personal information or privacy-relevant data elements are considered in scope.

| Data Element                            | Example or Description                             | Initial Privacy Relevance                                         |
| --------------------------------------- | -------------------------------------------------- | ----------------------------------------------------------------- |
| Name                                    | Customer first and last name                       | Direct identifier                                                 |
| Email address                           | Customer contact email                             | Direct identifier and communication channel                       |
| Phone number                            | Customer contact number                            | Direct identifier and communication channel                       |
| Address                                 | Customer address, if collected                     | Direct identifier with higher sensitivity depending on context    |
| Company name                            | Company or organization name, if applicable        | May identify an individual in some contexts                       |
| Reservation details                     | Booking date, class, number of participants, notes | Linked to customer activity and preferences                       |
| Contact message content                 | Free-text inquiry submitted by customer            | May contain unexpected personal information                       |
| Payment status                          | Paid, unpaid, pending, refunded, failed            | Payment-related operational information                           |
| Stripe transaction or payment reference | External payment reference or transaction ID       | Payment-related identifier and vendor processing link             |
| Admin/internal user identifiers         | Internal usernames, admin IDs, or access records   | Accountability and access governance information                  |
| System logs or access records           | Access, modification, deletion, or activity logs   | Accountability and incident investigation support                 |
| IP/device/session information           | Technical metadata, if collected or logged         | Privacy-relevant metadata if linked to an identifiable individual |

## 8. Data Stores and Processing Locations

The assessment assumes the following data stores or processing locations may be relevant.

| Location                            | Data Potentially Involved                                                        | Notes                                                               |
| ----------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Application database                | Reservation records, contact inquiries, customer identifiers, payment references | Primary internal storage location                                   |
| Payment processor environment       | Payment transaction data and related payment identifiers                         | External processing dependency                                      |
| Email service                       | Customer messages, notification content, operational communications              | May contain customer identifiers or message content                 |
| Admin interface                     | Customer records viewed or managed by internal users                             | Access control and logging relevance                                |
| Application logs                    | Activity records, errors, access events, metadata                                | Logging may be incomplete or limited                                |
| Version control/deployment workflow | Source code, configuration references, deployment history                        | Should not contain secrets or personal information                  |
| Cloud/media dependency              | Media or service-related assets, if used                                         | Scope depends on whether personal information is uploaded or stored |

## 9. Third-Party Dependencies

The assessment assumes the following third-party dependencies may be relevant.

| Third Party / Dependency                      | Assumed Function                         | Privacy Consideration                                             |
| --------------------------------------------- | ---------------------------------------- | ----------------------------------------------------------------- |
| Stripe or comparable payment processor        | Payment processing                       | Third-party processing, accountability, payment data boundary     |
| Gmail SMTP or comparable email service        | Email communication                      | Customer communication, message content, transmission pathway     |
| Cloudinary or comparable cloud/media service  | Media or file service dependency         | Vendor dependency and potential storage consideration             |
| GitHub or comparable version control platform | Source control and deployment support    | Change governance and secrets management                          |
| Hosting or deployment provider                | Application hosting                      | Infrastructure dependency and environment safeguard consideration |
| Database hosting provider, if applicable      | Data storage or managed database service | Storage, access, backup, and retention consideration              |

This project does not include a formal vendor audit. Vendor review is limited to documenting dependency, assumed data involvement, accountability considerations, and recommended documentation actions.

## 10. Assumptions

This assessment is based on the following assumptions:

1. The application is customer-facing and processes reservation and payment-related workflows.
2. The system collects personal information directly from customers through reservation and contact workflows.
3. The internal application stores reservation and contact-related records.
4. Payment processing is handled externally by Stripe or a comparable payment processor.
5. The internal system does not store full payment card data.
6. The internal system may retain payment status, reservation reference, or transaction reference information.
7. Internal users may access customer records for operational purposes.
8. Role-based access control may be incomplete or not fully documented.
9. Some customer contact fields may have stronger protection than other identifiable customer fields.
10. Audit logging may not fully capture who accessed, modified, exported, or deleted personal information.
11. Retention periods and deletion triggers may not be fully documented.
12. Vendor processing documentation may be incomplete or not centralized.
13. Evidence references are sanitized and used only for portfolio demonstration purposes.
14. No real customer data, credentials, secrets, production screenshots, or confidential business records are included.
15. The assessment is limited to privacy-relevant data handling and does not perform penetration testing, source code review, or full security testing.

## 11. Evidence Boundaries

The project uses mock, sanitized, or anonymized evidence references.

Evidence references may include:

* EV-001: Sanitized data model reference
* EV-002: Sanitized application workflow reference
* EV-003: Sanitized vendor dependency reference
* EV-004: Sanitized access review reference
* EV-005: Sanitized logging review reference
* EV-006: Sanitized retention review reference

These references are used to demonstrate evidence traceability and documentation discipline.

They do not represent confidential production evidence, real customer data, credentials, or proprietary business records.

## 12. Sanitization Rules

The following sanitization rules apply:

* No real customer personal information is included.
* No production credentials or secrets are included.
* No confidential business records are included.
* No proprietary screenshots are included.
* Any sample names, emails, phone numbers, addresses, transaction references, or logs are mock examples.
* Any system descriptions are generalized to avoid exposing confidential implementation details.
* Any technical findings are described at a privacy-risk level rather than exposing sensitive system details.

## 13. Privacy Assessment Boundaries

This assessment focuses on privacy-relevant data handling risks.

In scope:

* Personal information lifecycle review
* Collection and purpose analysis
* Storage and access analysis
* Third-party processing documentation
* Safeguards review
* Logging and accountability review
* Retention and deletion considerations
* Evidence traceability
* Privacy risk documentation
* Remediation tracking

Out of scope:

* Formal legal opinion
* Official Privacy Impact Assessment submission
* Certification of compliance
* Regulatory audit
* Full penetration test
* Full network security assessment
* Full source code review
* Full vendor audit
* Full data subject request program implementation
* Full breach response program implementation

## 14. Canadian Privacy Principles Used as Assessment Lens

This assessment uses Canadian privacy principles as a framework for analysis.

The primary assessment lens is PIPEDA Fair Information Principles, including:

* Accountability
* Identifying Purposes
* Consent
* Limiting Collection
* Limiting Use, Disclosure, and Retention
* Accuracy
* Safeguards
* Openness
* Individual Access
* Challenging Compliance

These principles are used to structure the assessment and map privacy-relevant findings.

This project does not claim that the application is compliant with PIPEDA or any other privacy law.

## 15. Key Privacy Questions Created by This Context

Based on the system context and assumptions, the assessment will examine the following questions:

1. What personal information is collected through each workflow?
2. Is the purpose of collection documented?
3. Is the collection limited to what is necessary for the workflow?
4. Where is each data element stored?
5. Who can access each category of personal information?
6. Is access limited by role and need-to-know?
7. Is any personal information processed by a third party?
8. What personal information remains in the internal system after third-party processing?
9. What safeguards apply to each data element?
10. Are safeguards consistently applied to comparable identifiable data?
11. Are access, modification, export, and deletion events logged?
12. Are retention periods and deletion triggers documented?
13. Is evidence available to support privacy findings?
14. Are remediation actions assigned and trackable?
15. Are breach triage considerations documented?

## 16. Link to Main Privacy Findings

This system context supports the following privacy-relevant findings that will be assessed later in the project.

| Finding ID | Finding Title                                                    | System Context Connection                                                                         |
| ---------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| PF-001     | Inconsistent Field-Level Protection                              | Customer contact fields may have stronger protection than other identifiable customer fields      |
| PF-002     | RBAC / Access Limitation Gap                                     | Internal/admin access may not be limited by role and need-to-know                                 |
| PF-003     | Limited Audit Logging                                            | Access, modification, export, or deletion of personal information may not be fully logged         |
| PF-004     | Stripe Third-Party Processing Dependency                         | Payment processing is externally dependent and internal retained data should be documented        |
| PF-005     | Retention / Deletion Documentation Incomplete                    | Reservation records, contact messages, and payment references may lack documented retention rules |
| PF-006     | Evidence Traceability Gap                                        | Evidence supporting privacy findings may not be centralized                                       |
| PF-007     | Change Management Risk for Systems Handling Personal Information | Changes affecting personal information systems may lack documented privacy review                 |

## 17. Limitations

This document has the following limitations:

* It is based on sanitized system assumptions.
* It does not confirm all production configurations.
* It does not include real customer records.
* It does not include confidential technical evidence.
* It does not include a full source code review.
* It does not include a full vendor audit.
* It does not validate whether all listed data elements are collected in production.
* It does not provide legal advice.
* It does not certify compliance with any privacy law.

## 18. How This Document Supports the Next Deliverables

This document provides the foundation for the next project deliverables.

| Next Deliverable                           | How This Document Supports It                                                                                         |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| 03_Personal_Information_Inventory.xlsx     | Defines the data elements, workflows, storage points, access roles, vendors, and assumptions needed for the inventory |
| 04_Data_Flow_Map.md                        | Defines the workflows and system components that will be mapped into privacy-relevant data flows                      |
| 05_PIA_Style_Privacy_Assessment.md         | Establishes the assessment context, boundaries, and assumptions                                                       |
| 06_Canadian_Privacy_Framework_Mapping.xlsx | Identifies the privacy principles that findings will be mapped against                                                |
| 07_Privacy_Safeguards_Gap_Log.xlsx         | Defines the safeguard areas that require review                                                                       |
| 08_Vendor_Processing_Assessment_Stripe.md  | Establishes the payment processor dependency and data boundary                                                        |
| 09_Privacy_Risk_Register.xlsx              | Provides the context needed to write defensible privacy risk statements                                               |
| 10_Remediation_Tracker.xlsx                | Defines the findings and gaps that will require remediation actions                                                   |
| 11_Evidence_Index.xlsx                     | Establishes the evidence reference structure                                                                          |
| 12_Executive_Summary.md                    | Provides the system background and assessment boundary for the final summary                                          |



## 19. Disclaimer

This document is part of a portfolio assessment created for professional demonstration and educational purposes.

It is not a formal legal opinion, official Privacy Impact Assessment, regulatory audit, certification, or compliance attestation.

All descriptions, evidence references, workflows, and assumptions are sanitized or generalized to avoid exposing real customer data, confidential business records, credentials, or proprietary system details.
