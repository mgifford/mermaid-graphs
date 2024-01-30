## Decision Tree

```mermaid
graph TD
    UserNeeds(identify user needs)-->DSC_MR(Fill in DSC market research tool);
    DSC_MR-->More_MR(Do other market research if necessary);

    More_MR-->CompanyPool(Are there enough eligible DSC companies?);
    CompanyPool-->DSC_Matrix(Check the DSC matrix: <br>who is on the GSA Schedule, <br>and are in the state);

    DSC_Matrix-->StateRepresentation(Verify that state representation <br>is actually needed);
    StateRepresentation-->DSC_InState{Are there enough state <br>based contract established <br>with DSC members};

    DSC_InState--> |Yes| UseStateContract(Use existing state based contracts);
    DSC_InState--> |No| Eligible4GSA_Schedule(Is this [contract eligibile](https://www.gsa.gov/policy-regulations/policy/acquisition-policy/eligibility-determinations) <br>for the GSA Schedule);

    UseStateContract-->ProcurementVehicle(Finalize procurement vehicle);
    Eligible4GSA_Schedule-->ProcurementVehicle;

    ProcurementVehicle-->IssueRFP(Issue the RFP/RFI);
    IssueRFP-->Negotiation(Negotiation and Award);
    Negotiation-->Payment(Payment Processing);
    Payment-->Reporting(Reporting and Compliance);
```
