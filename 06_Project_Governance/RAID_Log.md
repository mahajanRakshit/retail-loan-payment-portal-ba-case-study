# RAID Log

| ID | Type | Description | Impact | Proposed response | Owner (role) |
|---|---|---|---|---|---|
| R-01 | Risk | Eligibility rules are not confirmed by business stakeholders. | Incorrect indicative results | Obtain approved rule set and disclaimer before build. | Product Owner / Risk |
| R-02 | Risk | Payment callback is delayed or unavailable. | Customer may retry and create duplicate payment risk. | Keep status pending; define reconciliation and safe retry rules. | Technology / Payments |
| A-01 | Assumption | Bank has an existing authenticated customer portal. | Scope depends on current architecture. | Validate during discovery. | Product Owner |
| I-01 | Issue | Product-specific document matrix is not supplied in this simulation. | Checklist cannot be finalized. | Record as an open question; use placeholder configuration only. | Loan Operations |
| D-01 | Dependency | Payment provider integration contract and sandbox. | Payment flow cannot be fully validated. | Confirm provider API and test environment. | Technology |
| D-02 | Dependency | Bank loan system provides EMI schedule data. | Repayment display depends on source data. | Define data contract and error handling. | Technology / Loan Operations |
