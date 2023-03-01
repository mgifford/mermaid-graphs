# graph
Simple accessibility workflow


## Workflow 1

```mermaid
graph TD
    Start-->CheckoutCode;
    CheckoutCode-->SetupDDev;
    SetupDDev-->BuildSite;
    SetupDDev-->ImportDatabase;
    BuildSite-->AccessibilityTests;
    ImportDatabase-->AccessibilityTests;
    AccessibilityTests-->End;
```


## Workflow 2

```mermaid
graph TD
    Start-->CheckoutCode;
    CheckoutCode-->SetupDDev;
    SetupDDev-->BuildSite;
    SetupDDev-->ImportDatabase;
    BuildSite-->AccessibilityTests;
    ImportDatabase-->AccessibilityTests;
    AccessibilityTests-->CypressTests;
    CypressTests-->SonarQubeScan;
    SonarQubeScan-->PushCodeToAcquia;
    PushCodeToAcquia-->End;
```


## Workflow 3

```mermaid
graph TD
    Start-->CheckoutCode;
    CheckoutCode-->SetupDDev{Setup DDev};
    SetupDDev-->BuildSite;
    SetupDDev-->ImportDatabase;
    BuildSite-->AccessibilityTests;
    ImportDatabase-->AccessibilityTests;
    AccessibilityTests > |NoErrors{No Errors}| AccessibilityTestsOk[OK]
    AccessibilityTestsOk-->CypressTests;
    CypressTests-->SonarQubeScan;
    SonarQubeScan-->PushCodeToAcquia;
    PushCodeToAcquia-->End;
```

