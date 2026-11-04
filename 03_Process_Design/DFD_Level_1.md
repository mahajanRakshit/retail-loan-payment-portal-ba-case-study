# Data Flow Diagram – Level 1

```mermaid
flowchart TB
 C[Customer]
 O[Loan Operations]
 PSP[Payment Provider]
 NS[Notification Service]
 D1[(Customer Profile Store)]
 D2[(Application Store)]
 D3[(Document Metadata Store)]
 D4[(Payment History Store)]

 P1((1.0 Manage Profile))
 P2((2.0 Manage Documents))
 P3((3.0 Submit & Track Application))
 P4((4.0 Manage EMI Payment))
 P5((5.0 Send Notifications))

 C -->|Registration/profile data| P1
 P1 --> D1
 D1 --> P1
 P1 -->|Profile status| C

 C -->|Document upload| P2
 P2 --> D3
 D3 --> P2
 O -->|Document review result| P2
 P2 -->|Document status| C

 C -->|Application details| P3
 D1 -->|Verified profile data| P3
 D3 -->|Document status| P3
 P3 --> D2
 O -->|Review status| P3
 P3 -->|Reference and status| C

 C -->|Payment request| P4
 P4 -->|Payment initiation| PSP
 PSP -->|Verified response| P4
 P4 --> D4
 D4 --> P4
 P4 -->|Payment result / receipt| C

 P3 -->|Application event| P5
 P4 -->|Payment event| P5
 P5 --> NS
```

## Data stores
- D1: Customer profile
- D2: Loan application and status
- D3: Document metadata and review status
- D4: Payment transaction history

This is a conceptual DFD. A real solution would require detailed data classification, security design, integration contracts and bank architecture review.
