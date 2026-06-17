# EV-002: Sanitized Application Workflow Reference

## Purpose

This evidence reference supports the assessment of reservation, contact, checkout, payment, email, and logging workflows.

## Evidence Type

Sanitized workflow evidence reference.

## Related Findings

- PF-002: RBAC / Access Limitation Gap
- PF-004: Stripe Third-Party Processing Dependency
- PF-005: Retention / Deletion Documentation Incomplete
- PF-007: Change Management Risk for Systems Handling Personal Information

## Workflow Summary

| Workflow | Privacy-Relevant Observation |
|---|---|
| Reservation workflow | Customer identifiers and reservation details are collected and stored for booking operations |
| Contact form workflow | Contact information and free-text message content are collected and stored for response handling |
| Checkout workflow | Customer, reservation, order, and payment-related information are connected |
| Payment workflow | Stripe hosted checkout handles payment processing externally |
| Email workflow | Transactional email may duplicate personal information outside the main database |
| Logging workflow | System events may be logged, but privacy-relevant access activity requires stronger traceability |

## Sanitization Applied

- Routes and workflows are described at a high level.
- No real customer submissions are included.
- No production logs are included.
- No webhook payloads are included.
- No payment card information is included.

## Privacy Relevance

This evidence supports the data flow map and PIA-style assessment by showing where personal information is collected, processed, stored, shared with vendors, and duplicated across systems.

## Evidence Handling Note

This file provides a public-safe workflow evidence reference and should be linked from the Evidence Index.
