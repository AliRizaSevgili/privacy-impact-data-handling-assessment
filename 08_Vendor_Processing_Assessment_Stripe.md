# Vendor Processing Assessment: Stripe

## Privacy Impact & Data Handling Risk Assessment: Customer-Facing Reservation Platform

## 1. Purpose

The purpose of this document is to assess the privacy-relevant role of Stripe as a third-party payment processing dependency in the customer-facing reservation and payment-related application.

This assessment documents:

* Stripe's role in the payment workflow
* Personal information and payment-related metadata that may be involved
* What is processed externally by Stripe
* What may remain in the internal application
* Accountability considerations
* Safeguards considerations
* Contractual and documentation considerations
* Privacy risks and recommended actions
* Evidence references and limitations

This document does not audit Stripe's internal controls, certify Stripe compliance, or provide a formal vendor assurance opinion.

## 2. Assessment Scope

### 2.1 In Scope

This assessment covers:

* Stripe hosted checkout as a third-party payment processing dependency
* Payment-related data flow between the application and Stripe
* Internal retained payment-related metadata
* Webhook-based payment status updates
* Customer identifiers linked to payment or order records
* Vendor accountability documentation
* Privacy safeguards considerations
* Vendor processing evidence needs
* Recommended documentation and remediation actions

### 2.2 Out of Scope

The following items are outside the scope of this assessment:

* Formal audit of Stripe internal controls
* SOC report review of Stripe
* PCI DSS certification review
* Legal opinion on Stripe contractual terms
* Regulatory compliance conclusion
* Penetration testing of Stripe integration
* Full source code review of the payment integration
* Full vendor risk management program implementation
* Assessment of all Stripe products or services
* Assessment of unrelated third-party providers except where they interact with the payment workflow

## 3. Vendor Role

Stripe is used as the third-party payment processor for the checkout and payment workflow.

The application redirects customers to Stripe hosted checkout for payment processing. Payment details are processed externally by Stripe. The internal application is not assessed as storing full cardholder data.

Stripe's role in this project is therefore documented as:

| Area                      | Assessment Description                                                                                                                                   |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Vendor                    | Stripe                                                                                                                                                   |
| Vendor Type               | Third-party payment processor                                                                                                                            |
| Primary Workflow          | Checkout and payment workflow                                                                                                                            |
| Processing Role           | External hosted payment processing                                                                                                                       |
| Internal Application Role | Collects customer and reservation information, creates or updates order and reservation records, and may retain payment status or transaction references |
| Cardholder Data Boundary  | Full cardholder data is not assessed as stored in the internal application                                                                               |
| Evidence Basis            | Sanitized data flow and testing evidence                                                                                                                 |

## 4. Payment Workflow Summary

The payment workflow is assessed as follows:

```text
Customer
to Checkout Form
to Backend Route: save-checkout-info
to MongoDB infos, orders, or reservations collections
to Stripe Hosted Checkout
to Stripe Payment Processing
to Stripe Webhook Events
to Internal Application
to Order or Reservation Update
to Gmail SMTP Confirmation Email
```

Key workflow observations:

* The customer initiates payment from the application checkout workflow.
* The customer is redirected to Stripe hosted checkout.
* Payment details are processed externally by Stripe.
* The internal application may retain payment status, transaction reference, customer identifiers, reservation details, order records, or payment amount.
* Stripe webhook events may return payment-related status or transaction metadata to the internal application.
* Upon successful payment, the system may create an order record and update reservation status.
* A confirmation email may be sent to the customer through Gmail SMTP or a comparable email service.

## 5. Personal Information and Payment-Related Data Involved

The following data elements may be involved in the Stripe-related payment workflow.

| Data Element                  | Internal Application                   | Stripe Processing                                                | Privacy Relevance                               |
| ----------------------------- | -------------------------------------- | ---------------------------------------------------------------- | ----------------------------------------------- |
| First name                    | May be collected and stored internally | May be included in payment-related metadata or checkout context  | Direct identifier                               |
| Last name                     | May be collected and stored internally | May be included in payment-related metadata or checkout context  | Direct identifier                               |
| Email address                 | May be collected and stored internally | May be used for payment communication or customer identification | Direct identifier and communication channel     |
| Contact number                | May be collected and stored internally | May be included depending on checkout configuration              | Contact identifier                              |
| Address                       | May be collected and stored internally | May be included depending on checkout or billing configuration   | Direct identifier with increased privacy impact |
| Company information           | May be collected if provided           | May be included if connected to checkout metadata                | May identify an individual in some contexts     |
| Reservation details           | Stored internally                      | May be included as payment-related metadata or reference         | Links payment to customer activity              |
| Payment status                | Retained internally                    | Generated or confirmed through Stripe events                     | Payment-related operational information         |
| Stripe transaction reference  | Retained internally as a reference     | Generated by Stripe                                              | External payment reference                      |
| Order record                  | Created or updated internally          | Not an internal Stripe control item                              | Links customer, reservation, and payment status |
| Payment amount or order total | Retained internally                    | Processed by Stripe                                              | Transaction-related information                 |
| Cardholder data               | Not assessed as stored internally      | Processed externally by Stripe hosted checkout                   | Sensitive payment information                   |

## 6. Internal and External Data Boundary

### 6.1 Data Processed Externally by Stripe

Stripe is expected to process payment details through its hosted checkout environment.

This may include:

* Payment card or payment method details
* Payment authorization data
* Payment transaction processing data
* Payment confirmation or failure status
* Stripe-generated payment identifiers
* Payment-related metadata configured by the application

The assessment does not evaluate Stripe's internal processing, control environment, certifications, or compliance posture.

### 6.2 Data Retained or Processed Internally

The internal application may retain or process:

* Customer first name and last name
* Email address
* Contact number
* Address
* Company information, if provided
* Reservation details
* Order record
* Payment status
* Stripe transaction or payment reference
* Payment amount or order total
* Webhook event result or payment confirmation status

The internal application should document which payment-related elements are retained, why they are retained, where they are stored, who can access them, and when they should be deleted or archived.

## 7. Accountability Considerations

Under a Canadian privacy-principles-based assessment, the organization should be able to demonstrate accountability for third-party processing dependencies.

For this project, accountability considerations include:

| Accountability Area       | Assessment Consideration                                                                                          |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Vendor inventory          | Stripe should be listed in a vendor inventory with its role, data involved, and business purpose                  |
| Data processing boundary  | The organization should document what Stripe processes externally and what the internal application retains       |
| Contractual documentation | Relevant contractual, privacy, security, and data processing terms should be identified and referenced            |
| Access ownership          | Internal owner for Stripe dashboard or account access should be documented                                        |
| Access review             | Stripe access should be included in periodic access reviews                                                       |
| Evidence tracking         | Vendor-related evidence should be indexed and linked to privacy findings                                          |
| Retention                 | Internal payment references should have defined retention and deletion expectations                               |
| Incident readiness        | Privacy incident triage should consider Stripe-related events, payment metadata, and internal retained references |

## 8. Safeguards Considerations

Stripe hosted checkout reduces the internal application's handling of full cardholder data. However, this does not remove the need to protect payment-related metadata and customer identifiers retained internally.

### 8.1 Safeguards Observed or Expected

| Safeguard Area           | Assessment Note                                                                            |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| Hosted checkout          | Payment details are processed externally through Stripe hosted checkout                    |
| Cardholder data boundary | Full cardholder data is not assessed as stored in the internal application                 |
| Payment status handling  | Internal system may retain payment status or transaction reference                         |
| Webhook processing       | Webhook events may update order or reservation records                                     |
| Access restriction       | Stripe dashboard and internal payment records should be restricted to authorized personnel |
| Secrets management       | Stripe keys should be stored securely and access should be limited                         |
| Logging                  | Payment-related events should be logged without unnecessary personal information           |
| Retention                | Payment references should have documented retention rules                                  |

### 8.2 Safeguard Gaps

| Gap                                                                 | Privacy Impact                                                                                    |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Stripe processing boundary not fully documented                     | Organization may not clearly demonstrate what is processed externally and what remains internally |
| Internal retained payment metadata not centralized in documentation | Payment-related personal information may be difficult to govern or retrieve                       |
| No formal vendor risk assessment evidence identified                | Vendor accountability evidence may be incomplete                                                  |
| Stripe access not integrated into centralized access governance     | Payment-related information access may not be reviewed consistently                               |
| Webhook and payment event logging not mapped to privacy needs       | Incident investigation may be incomplete                                                          |
| Retention rules for payment references not fully documented         | Payment-related information may be retained longer than necessary                                 |
| Secrets access may be broad                                         | Stripe keys or related credentials may increase breach exposure if misused or compromised         |

## 9. Contractual and Documentation Considerations

This assessment does not review Stripe contracts or legal terms.

However, the following documentation should be maintained by the organization for accountability purposes:

| Documentation Item                  | Purpose                                                                                         |
| ----------------------------------- | ----------------------------------------------------------------------------------------------- |
| Vendor inventory entry              | Identify Stripe as a payment processor dependency                                               |
| Business purpose                    | Explain why Stripe is used                                                                      |
| Data elements processed             | Document what customer and payment-related data may be processed by Stripe                      |
| Internal retained data list         | Document payment metadata and references retained internally                                    |
| Access ownership record             | Identify who owns Stripe access and who can view payment records                                |
| Vendor terms reference              | Maintain link or reference to applicable Stripe terms, privacy terms, and data processing terms |
| Security documentation reference    | Maintain available vendor security documentation or assurance references where reviewed         |
| Incident contact or escalation path | Document how Stripe-related incidents would be escalated                                        |
| Retention note                      | Document retention of internal payment references and order records                             |
| Evidence reference                  | Link vendor evidence to the Evidence Index                                                      |

## 10. Privacy Risk Observations

### VPR-001: Stripe Processing Boundary Not Fully Centralized

| Field              | Assessment                                                                                                                                                                       |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Observation        | Stripe is used for hosted checkout, but the application should maintain centralized documentation showing what Stripe processes externally and what the internal system retains. |
| Privacy Risk       | Payment-related personal information may be difficult to govern if processing boundaries are unclear.                                                                            |
| Related Finding    | PF-004                                                                                                                                                                           |
| Related Principle  | Accountability, Openness, Limiting Use, Disclosure, and Retention                                                                                                                |
| Recommended Action | Create a Stripe processing record documenting data elements, business purpose, internal retained data, access owner, retention expectation, and evidence reference.              |
| Priority           | Medium                                                                                                                                                                           |

### VPR-002: Internal Retained Payment Metadata Requires Governance

| Field              | Assessment                                                                                                                                                     |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Observation        | Payment status, transaction references, order records, reservation linkage, and payment amount may remain in the internal application after Stripe processing. |
| Privacy Risk       | Payment-related metadata may become privacy-relevant when linked to identifiable customer records.                                                             |
| Related Finding    | PF-004, PF-005                                                                                                                                                 |
| Related Principle  | Accountability, Safeguards, Limiting Use, Disclosure, and Retention                                                                                            |
| Recommended Action | Define retention, access, logging, and deletion expectations for internal payment metadata.                                                                    |
| Priority           | Medium                                                                                                                                                         |

### VPR-003: Vendor Risk Evidence Not Documented

| Field              | Assessment                                                                                                                                                                 |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Observation        | No formal vendor risk assessment, due diligence documentation, or ongoing monitoring evidence was identified for Stripe, Cloudinary, or Gmail in the ITGC testing context. |
| Privacy Risk       | The organization may lack evidence to demonstrate vendor accountability and third-party processing oversight.                                                              |
| Related Finding    | PF-004, PF-006                                                                                                                                                             |
| Related Principle  | Accountability, Safeguards, Openness                                                                                                                                       |
| Recommended Action | Maintain vendor assessment evidence, terms references, security documentation references, and periodic review notes.                                                       |
| Priority           | Medium                                                                                                                                                                     |

### VPR-004: Stripe Access Governance Should Be Documented

| Field              | Assessment                                                                                                                                |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Observation        | Third-party access is fragmented, with Stripe access identified as owned by the Founder in the access mapping context.                    |
| Privacy Risk       | Payment-related information access may not be governed consistently if Stripe access is not included in a centralized access review.      |
| Related Finding    | PF-002, PF-004                                                                                                                            |
| Related Principle  | Accountability, Safeguards                                                                                                                |
| Recommended Action | Include Stripe account access in periodic access reviews and document access owner, role, business justification, and revocation process. |
| Priority           | Medium                                                                                                                                    |

### VPR-005: Stripe Keys and Payment Integration Secrets Require Restricted Access

| Field              | Assessment                                                                                                                                            |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Observation        | Sensitive credentials, including Stripe keys, may be stored in environment variables and accessible through development or deployment configurations. |
| Privacy Risk       | Broad access to payment integration secrets could increase exposure if credentials are misused or compromised.                                        |
| Related Finding    | PF-001, PF-002                                                                                                                                        |
| Related Principle  | Safeguards, Accountability                                                                                                                            |
| Recommended Action | Restrict access to Stripe keys, rotate credentials where appropriate, document owners, and review deployment environment access.                      |
| Priority           | High                                                                                                                                                  |

## 11. Recommended Actions

| Action ID | Recommended Action                                                                                                            | Priority      | Owner                                | Evidence Required        |
| --------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------ | ------------------------ |
| VA-001    | Create a Stripe vendor inventory entry with business purpose, data elements, access owner, and evidence references            | Medium        | Vendor / Third-Party Owner           | Vendor inventory record  |
| VA-002    | Document Stripe processing boundary and internal retained payment metadata                                                    | Medium        | Privacy Reviewer / Application Owner | Stripe processing record |
| VA-003    | Identify and retain relevant Stripe contractual, privacy, security, and data processing terms references                      | Medium        | Vendor / Third-Party Owner           | Terms reference record   |
| VA-004    | Include Stripe account access in periodic access reviews                                                                      | Medium        | Business Owner / Application Owner   | Access review record     |
| VA-005    | Restrict and document access to Stripe keys and payment integration secrets                                                   | High          | Application Owner / Technical Owner  | Secrets access review    |
| VA-006    | Define retention and deletion expectations for payment status, transaction references, order records, and reservation linkage | Medium        | Privacy Reviewer / Business Owner    | Retention matrix         |
| VA-007    | Confirm that payment-related logs avoid unnecessary personal information                                                      | Medium        | Technical Owner                      | Logging review evidence  |
| VA-008    | Document incident escalation steps for Stripe-related payment or privacy events                                               | Low to Medium | Privacy Reviewer / Business Owner    | Incident triage note     |
| VA-009    | Link Stripe vendor evidence to the central Evidence Index                                                                     | Medium        | Privacy Reviewer                     | Evidence index entry     |

## 12. Evidence References

| Evidence ID | Evidence Name                            | Relevance                                                                         |
| ----------- | ---------------------------------------- | --------------------------------------------------------------------------------- |
| EV-002      | Sanitized application workflow reference | Supports checkout, payment, webhook, order, and confirmation email flow           |
| EV-003      | Sanitized vendor dependency reference    | Supports Stripe vendor dependency and third-party processing assessment           |
| EV-004      | Sanitized access review reference        | Supports Stripe access governance and third-party access ownership considerations |
| EV-005      | Sanitized logging review reference       | Supports payment event logging and incident investigation considerations          |
| EV-006      | Sanitized retention review reference     | Supports payment metadata and order record retention considerations               |

## 13. Limitations

This assessment has the following limitations:

* It is based on sanitized system context and evidence references.
* It does not include real customer data.
* It does not include confidential production evidence.
* It does not review Stripe contracts or legal terms directly.
* It does not audit Stripe internal controls.
* It does not review Stripe SOC reports.
* It does not certify PCI DSS compliance.
* It does not certify PIPEDA compliance.
* It does not perform penetration testing of the Stripe integration.
* It does not perform full source code review.
* It does not assess all Stripe products or configurations.
* It does not provide legal advice or a formal vendor assurance opinion.

## 14. Disclaimer

This document is part of a portfolio assessment created for professional demonstration and educational purposes.

It is not a formal legal opinion, official Privacy Impact Assessment, regulatory audit, vendor audit, certification, or compliance attestation.

All descriptions, evidence references, data flows, risks, and recommendations are sanitized or generalized to avoid exposing real customer data, confidential business records, credentials, vendor contracts, or proprietary implementation details.
