

## Decision Tree

- other market research if necessary
- find good companies, how would I find companies to do this
- look at DSC matrix and see who is on schedule and if any are in the state
- in state representation (is it needed)
- is there a state based contract established with members of the DSC on it
- Check which companies are on the GSA schedule
- Eligibility determination
- Vehicle decision made - procurement vehicle
- Issue the RFP



```mermaid
graph TD
    UserNeeds(identify user needs)-->DSC_MR(Fill in DSC market research tool);
    DSC_MR-->Wireframe;
    Wireframe-->ProactiveAccessibilityTestingWireframe;
    ProactiveAccessibilityTestingWireframe-->ProductBacklog;
    ProductBacklog-->SprintBacklog;
    ProductBacklog-->ProactiveAccessibilityTestingUXDesign;
    ProductBacklog-->ProactiveAccessibilityTestingUXResearch;
    ProactiveAccessibilityTestingUXDesign-->Wireframe;
    ProactiveAccessibilityTestingUXResearch-->UXResearchReactive;
    UXResearchReactive-->ReactiveAccessibilityTesting;
    ReactiveAccessibilityTesting-->DeployedSystem;
    SprintBacklog-->Sprint;
    Sprint-->Scrum;
    Scrum-->ProaciveAccessibilityTestingSprint;
    ProaciveAccessibilityTestingSprint-->ShipableProduct;
    ShipableProduct-->AccessibilityValidationTesting;
    AccessibilityValidationTesting-->DeployedSystem;
```
