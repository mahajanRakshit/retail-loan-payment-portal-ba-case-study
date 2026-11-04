# User Stories and Acceptance Criteria

## Epic 1: Customer onboarding

### US-01 – Register and create profile
**As a** prospective customer, **I want** to register and complete my profile, **so that** I can begin a loan application.

Acceptance criteria:
- Given I am a new customer, when I provide all mandatory valid details and complete the approved verification step, then my profile is created.
- Given a mandatory field is missing or invalid, when I submit the form, then the system highlights the field and explains the correction.
- Given my profile is incomplete, when I leave the journey, then the system follows the agreed draft-save behaviour.

### US-02 – View document checklist
**As a** loan applicant, **I want** to see the documents required for my selected product, **so that** I can prepare a complete application.

Acceptance criteria:
- Given I select a loan product, when the checklist loads, then only the configured required document types are shown.
- Given a document has not been uploaded, then its status is shown as Not Uploaded.
- Given a document is rejected, then the reason and next action are displayed when supplied by Operations.

## Epic 2: Eligibility and application

### US-03 – Check preliminary eligibility
**As a** customer, **I want** to enter the required information and see an indicative eligibility result, **so that** I understand whether I may proceed.

Acceptance criteria:
- Given all required inputs are valid, when I request a check, then the portal displays the configured indicative result.
- The result clearly states that it is not a final loan approval.
- Given required inputs are missing, then the portal identifies the missing fields and does not calculate a result.

### US-04 – Submit loan application
**As a** customer, **I want** to submit a complete application, **so that** the bank can review it.

Acceptance criteria:
- Given mandatory profile details and required documents are complete, when I submit, then the system creates an application record.
- The system generates and displays a unique application reference.
- Given mandatory information is missing, then submission is blocked and the missing items are shown.
- Repeated submission attempts must not unintentionally create duplicate applications.

### US-05 – Track application status
**As a** customer, **I want** to track my application, **so that** I know its current stage and whether I need to act.

Acceptance criteria:
- Given I am authenticated, when I open My Applications, then I see only applications associated with my customer identity.
- Each application displays its latest status and last-updated timestamp.
- If customer action is required, the portal displays the action and relevant guidance.

## Epic 3: EMI payments

### US-06 – View EMI schedule
**As a** borrower, **I want** to view my EMI amount and due dates, **so that** I can plan repayments.

Acceptance criteria:
- Given an eligible loan account is available, when I open Repayments, then the schedule supplied by the bank system is displayed.
- The amount, due date and payment status are clearly labelled.
- If schedule data is unavailable, the portal shows a helpful message rather than invented values.

### US-07 – Make EMI payment
**As a** borrower, **I want** to initiate an EMI payment, **so that** I can repay an amount due.

Acceptance criteria:
- Given a valid due amount is payable, when I choose Pay, then the portal initiates a request with the approved provider.
- Until verified confirmation is received, the status remains Pending.
- Given the provider confirms success, then the portal records the transaction reference and displays a receipt.
- Given the provider confirms failure, then the portal displays Failed and the approved next step.
- A timeout must not be treated as success; the portal must follow the agreed reconciliation process before allowing a potentially duplicate retry.

### US-08 – View payment history
**As a** borrower, **I want** to view previous payments, **so that** I can confirm my repayment records.

Acceptance criteria:
- Given I am authenticated, when I open Payment History, then I see only my own transactions.
- Each record shows date, amount, status and available transaction reference.
- A receipt is available only for a confirmed successful payment.

## Epic 4: Operations

### US-09 – Review application and update status
**As an** authorized loan operations user, **I want** to review an application and update its status, **so that** the customer receives an accurate progress update.

Acceptance criteria:
- Given I have the required role, when I open an assigned application, then I can view permitted application and document details.
- I can update only statuses allowed by the configured workflow and my role.
- Each status change records actor, timestamp and status transition.
- Unauthorized users cannot change application status.
