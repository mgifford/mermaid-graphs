# Service Design Blueprint Idea
Can we do this in Mermaid


## Rough Workflow

```mermaid
sequenceDiagram
    par
        Phase 1->>Phase 2: Discovery
        Phase 2->>Phase 3: QA
        Phase 3->>Phase 4: Launch

    and
        Phase 1->>Phase 4: Evidence
    and
        Phase 1->>Phase 4: Customer Actions
    and
        Phase 1->>Phase 4: Frontstage Actions
    and
        Phase 1->>Phase 4: Backstage Actions
    and
        Phase 1->>Phase 4: Support Processes
    and
        Phase 1->>Phase 3: Internal
        par 
            Phase 3->>Phase 4: Soft Launch
            Phase 4->>Phase 3: Hard Launch
        end
        Phase 1->>Phase 3: Launch
    end
```
