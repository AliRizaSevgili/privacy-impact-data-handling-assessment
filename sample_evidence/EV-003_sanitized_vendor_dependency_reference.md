# EV-003: Sanitized Vendor Dependency Reference

## Purpose

This evidence reference supports the assessment of third-party processing dependencies used by the application.

## Evidence Type

Sanitized vendor dependency reference.

## Related Findings

- PF-004: Stripe Third-Party Processing Dependency
- PF-006: Evidence Traceability Gap

## Vendor Dependency Summary

| Vendor / Dependency | Role | Privacy-Relevant Consideration |
|---|---|---|
| Stripe | Hosted checkout and payment processing | Payment details are processed externally, while internal payment metadata may remain privacy-relevant |
| Gmail SMTP | Transactional email communication | Emails may contain customer identifiers, reservation details, order details, or inquiry content |
| Cloudinary | Media handling | Primarily non-sensitive in this context, but vendor role should be documented |
| Render | Hosting and deployment | Environment access and deployment configuration may affect safeguards |
| GitHub | Source control and deployment workflow | Change governance and secrets handling considerations |
| MongoDB / database context | Application data storage | Storage, access, retention, and deletion considerations |

## Sanitization Applied

- No vendor contracts included.
- No account screenshots included.
- No production credentials included.
- No customer payment records included.
- No proprietary vendor configuration details included.

## Privacy Relevance

This evidence supports vendor accountability analysis and third-party processing documentation. It does not audit vendor controls or certify vendor compliance.

## Evidence Handling Note

This file should be used as a public-safe vendor dependency reference and linked to the Stripe vendor assessment and Evidence Index.
