# Impact Direction for Sales

There are multiple ways to think about how to apporach this.

## Agency Workflow 2

```mermaid
graph TD
    CheckColor-->IsGreen{{Proceed}};
    CheckColor-->isYellow[Collaborate];
    CheckColor-->isJustificationRequired["Justification Required"];
    isYellow-->salesAlertsImpactsl["Sales Sends a message to @impact-committee in #sales-impact"];
   salesAlertsImpacts-->ImpactResponds["Point person from Impact acknowledges the request. (80% SLA in 1 day, others in 3 days)"];
   ImpactResponds-->ImpactDiscusses["Point person facilitates the discussion in the Impact committee. Possibly using a rubric."];
  ImpactDiscusses-->Decision["Impact committee decides & communicates to Sales."];


```

## Values workflow 2

```mermaid
graph TD
   DITAP-->Tier1;
   Accessibility[[Accessibility Focus]]-->Tier1;
   Sustainability[[Environmental Sustainability Focus]]-->Tier1;
   Open[[Open Government Focus]]-->Tier1;
   Tier1[[T1 Values aligned]]-->Yes;
   Tier2[[T2 Organization aligned]]-->Yes
   Tier3[[T3 Smaller]]-->Maybe
```

## Values workflow 3

```mermaid
graph TD
   DITAP-->Tier1;
   Accessibility[[Accessibility Focus]]-->Tier1;
   Sustainability[[Environmental Sustainability Focus]]-->Tier1;
   Open[[Open Government Focus]]-->Tier1;
   Tier1[[T1 Values aligned]]-->Yes;
   Tier2[[T2 Organization aligned]]-->Yes
   Tier3[[T3 Smaller]]-->Maybe
```
