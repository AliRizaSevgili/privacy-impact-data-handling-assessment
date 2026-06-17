# EV-001: Sanitized Data Model Reference

## Purpose

This evidence reference supports the assessment of personal information fields, data model handling, and field-level protection coverage.

## Evidence Type

Sanitized technical evidence reference.

## Related Findings

- PF-001: Inconsistent Field-Level Protection
- PF-002: RBAC / Access Limitation Gap
- PF-006: Evidence Traceability Gap

## Data Elements Referenced

| Data Element | Privacy Relevance | Protection Observation |
|---|---|---|
| First name | Direct identifier | Plaintext storage observed in sanitized model review |
| Last name | Direct identifier | Plaintext storage observed in sanitized model review |
| Email address | Direct identifier and communication channel | Field-level encryption observed |
| Contact number | Direct identifier and communication channel | Field-level encryption observed |
| Address | Direct identifier with increased privacy impact | Plaintext storage observed in sanitized model review |
| Company information | May identify an individual in some contexts | Plaintext storage observed where provided |

## Sanitization Applied

- No real customer records included.
- No database export included.
- No credentials included.
- Field names generalized where necessary.
- Implementation details limited to privacy-relevant observations.

## Privacy Relevance

This evidence supports the conclusion that comparable identifiable customer fields may not receive consistent protection. It supports safeguards analysis without claiming legal non-compliance.

## Evidence Handling Note

This file is an evidence reference, not a confidential source artifact. It is suitable for a public portfolio repository because it does not expose real customer data or proprietary implementation details.
