# Business Requirements Document (BRD)

## 1. Document purpose
This BRD defines the business need, objectives, scope, stakeholders and high-level requirements for the fictional Retail Loan & Payment Portal Enhancement.

## 2. Current business situation
Customers use a digital portal to begin a personal-loan application and make repayments. The assumed current experience has limited guidance, unclear document status, limited application tracking and insufficiently clear payment outcomes.

## 3. Business needs
- BN-01: Customers need a guided onboarding process.
- BN-02: Customers need to know which documents are required and whether each has been received.
- BN-03: Customers need visibility into application progress.
- BN-04: Customers need access to their EMI schedule and payment history.
- BN-05: Customers need clear confirmation or next steps when a payment is pending or fails.
- BN-06: Operations teams need consistent application statuses and an audit trail of important actions.

## 4. High-level business requirements
| ID | Requirement | Priority |
|---|---|---|
| BR-01 | The portal shall guide customers through registration and profile completion. | Must |
| BR-02 | The portal shall display a product-specific document checklist. | Must |
| BR-03 | The portal shall show preliminary eligibility results using approved business rules. | Must |
| BR-04 | The portal shall generate an application reference number after successful submission. | Must |
| BR-05 | Customers shall be able to view application status and pending actions. | Must |
| BR-06 | Customers shall be able to view EMI schedule and due dates. | Must |
| BR-07 | Customers shall be able to initiate an EMI payment through an approved payment provider. | Must |
| BR-08 | The portal shall display payment status and a transaction reference/receipt where available. | Must |
| BR-09 | The portal shall notify customers of material application and payment events. | Should |
| BR-10 | Authorized operations users shall be able to view application details and update permitted review statuses. | Should |

## 5. Business rules (illustrative)
- A customer must complete mandatory profile fields before submitting an application.
- Required documents depend on the selected loan product and the bank's approved policy.
- A preliminary eligibility result is indicative only; final approval requires the bank's formal assessment.
- Each submitted application receives a unique reference number.
- A payment is marked successful only after confirmation from the payment provider.
- Pending or failed transactions must not be represented as successful.
- Customers may view only their own application and payment information.
- Changes to application status must be attributable to an authorized user or system event.

## 6. High-level process
Customer registers → completes profile → selects loan product → checks preliminary eligibility → uploads documents → submits application → tracks review status → views EMI schedule (when applicable) → initiates payment → receives status/receipt.

## 7. Out of scope
Automated final credit decisions, loan sanction, disbursement, collections, actual payment processing implementation, credit bureau connectivity and production integrations.

## 8. Risks and dependencies
- Eligibility rules must be supplied and approved by the bank.
- Payment status depends on provider callback/confirmation design.
- Document requirements vary by product and customer category.
- Security, consent, privacy and retention rules require specialist approval.

## 9. Acceptance of BRD
In a real project, the Product Owner, Operations, Compliance/Risk and relevant technology stakeholders would review and approve this document before detailed design.
