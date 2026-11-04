# TO-BE Workflow (Proposed Future State)

```mermaid
flowchart TD
 A([Customer opens portal]) --> B[Register / sign in securely]
 B --> C[Complete guided profile]
 C --> D{Profile valid?}
 D -- No --> E[Show field-level validation]
 E --> C
 D -- Yes --> F[Select loan product]
 F --> G[Run preliminary eligibility check]
 G --> H[Show indicative result and disclaimer]
 H --> I[Display product-specific document checklist]
 I --> J[Upload required documents]
 J --> K{Mandatory items complete?}
 K -- No --> L[Show missing/rejected items and next action]
 L --> J
 K -- Yes --> M[Submit application]
 M --> N[Generate unique reference number]
 N --> O[Show confirmation and trackable status]
 O --> P[Operations review and authorized status update]
 P --> Q[Notify customer of material updates]
 Q --> R{Loan proceeds to repayment stage?}
 R -- No --> S([Customer follows application outcome])
 R -- Yes --> T[Display EMI schedule and due dates]
 T --> U[Customer initiates EMI payment]
 U --> V[Await verified provider response]
 V --> W{Payment confirmed?}
 W -- Yes --> X[Show success, reference and receipt]
 W -- No --> Y[Show pending/failed state and safe next step]
 X --> Z[Update payment history]
 Y --> Z
 Z --> AA([Journey completed])
```

## Expected improvement
The proposed flow gives customers clearer next actions, visible application status and more transparent payment outcomes. These are intended benefits, not measured results.
