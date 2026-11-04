# Functional Requirements Document (FRD)

## 1. Purpose
Translate the approved high-level business needs into functional behaviour for the portal. This is a proposed design for a fictional case study.

## 2. Actors
- Customer
- Loan Operations User
- Notification Service
- Payment Service Provider (external)
- Portal System

## 3. Functional requirements

### Module A: Registration and profile
| ID | Functional requirement | Priority |
|---|---|---|
| FR-001 | The system shall allow a customer to register using the bank-approved identifier and contact verification process. | Must |
| FR-002 | The system shall validate mandatory profile fields and display field-level errors. | Must |
| FR-003 | The system shall allow a customer to save an incomplete application as a draft. | Should |

### Module B: Document management
| ID | Functional requirement | Priority |
|---|---|---|
| FR-004 | The system shall display the document checklist based on the selected product and approved policy configuration. | Must |
| FR-005 | The system shall allow supported document files to be uploaded against the relevant checklist item. | Must |
| FR-006 | The system shall display each document's status as Not Uploaded, Uploaded, Under Review, Accepted or Rejected. | Must |
| FR-007 | The system shall display a reason or action request when a document is rejected, where provided by Operations. | Should |

### Module C: Eligibility and application submission
| ID | Functional requirement | Priority |
|---|---|---|
| FR-008 | The system shall collect the inputs required for a preliminary eligibility check. | Must |
| FR-009 | The system shall display an indicative result and a clear disclaimer that it is not final loan approval. | Must |
| FR-010 | The system shall prevent submission when mandatory fields or required documents are missing. | Must |
| FR-011 | The system shall create an application record and unique reference number after successful submission. | Must |
| FR-012 | The system shall display a submission confirmation with the reference number. | Must |

### Module D: Application tracking
| ID | Functional requirement | Priority |
|---|---|---|
| FR-013 | The customer shall be able to view the status of their submitted application. | Must |
| FR-014 | The system shall show the latest status, last updated date/time and any pending customer action. | Must |
| FR-015 | Authorized Operations users shall be able to update only the statuses permitted by their role. | Should |

### Module E: EMI and payments
| ID | Functional requirement | Priority |
|---|---|---|
| FR-016 | The system shall display the EMI amount, due date and schedule supplied by the bank's loan system. | Must |
| FR-017 | The customer shall be able to initiate a payment for an eligible due amount. | Must |
| FR-018 | The system shall display Pending until a definitive payment confirmation is received. | Must |
| FR-019 | The system shall display Success or Failed based on verified provider confirmation. | Must |
| FR-020 | The system shall display a transaction reference and receipt for confirmed successful payments. | Must |
| FR-021 | The system shall maintain a customer-visible payment history. | Should |

### Module F: Notifications
| ID | Functional requirement | Priority |
|---|---|---|
| FR-022 | The system shall trigger a notification for application submission and material status changes. | Should |
| FR-023 | The system shall trigger a payment confirmation or failure notification based on verified payment status. | Should |

## 4. Non-functional requirements
| ID | Category | Requirement |
|---|---|---|
| NFR-01 | Security | Access to customer records must be authenticated and authorized. |
| NFR-02 | Privacy | Sensitive data must be handled according to bank-approved privacy and retention policies. |
| NFR-03 | Auditability | Important status changes and payment events must be logged with timestamp and actor/source. |
| NFR-04 | Availability | Service availability targets must be agreed with business and technology teams. |
| NFR-05 | Usability | Forms must provide clear labels, validation messages and accessible navigation. |
| NFR-06 | Performance | Response-time targets must be defined and validated during non-functional testing. |
| NFR-07 | Reliability | Payment status must be reconciled against the provider's verified response; uncertain outcomes must remain pending. |

## 5. Key data fields (illustrative)
Customer: Customer ID, full name, verified contact, address, consent status.
Application: Application ID, customer ID, product, requested amount, tenure, submission date, status, pending action.
Document: Document ID, application ID, document type, upload timestamp, review status, review note.
Payment: Payment ID, loan/application reference, amount, due date, provider reference, status, timestamp.

Do not use real customer or account data in this portfolio.

## 6. Exception scenarios
- Invalid or missing mandatory profile information.
- Unsupported or unreadable document upload.
- Required document rejected and resubmission requested.
- Preliminary eligibility inputs incomplete.
- Duplicate submit attempt.
- Payment provider timeout or delayed callback.
- Payment failed or status remains pending.
- Customer attempts to access another customer's record.

## 7. Open questions for stakeholder validation
1. What exact fields and documents are mandatory for each loan product?
2. What are the approved preliminary eligibility rules and disclaimers?
3. Which application statuses and status transitions are permitted?
4. Which payment provider and confirmation mechanism are used?
5. What are the retry, duplicate-payment and reconciliation rules?
6. What are the retention, consent, audit and accessibility requirements?
