# Data Flow Diagram – Context Level

```mermaid
flowchart LR
 C[Customer] -->|Profile, application, documents, payment request| P((Retail Loan & Payment Portal))
 P -->|Status, checklist, EMI schedule, receipt| C
 O[Loan Operations] -->|Review outcome and status updates| P
 P -->|Application details and work queue| O
 PSP[Payment Service Provider] -->|Verified payment response| P
 P -->|Payment initiation request| PSP
 N[Notification Service] <-->|Notification event / delivery status| P
 L[Bank Loan System] <-->|Loan account and EMI schedule data| P
```

## External entities
Customer, Loan Operations, Payment Service Provider, Notification Service and Bank Loan System.

## Main system boundary
The portal coordinates customer-facing journeys. Actual credit decisions, payment settlement and authoritative loan servicing remain with bank-controlled systems and approved providers.
