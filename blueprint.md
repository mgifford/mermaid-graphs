# Service Design Blueprint Idea
Can we do this in Mermaid


## Rough Workflow

```mermaid
sequenceDiagram
    par 
        UI->>Backend: Request for items
    Backend->>UI: Items returned
    and 
        UI->>Cart Service: Fetch items in cart
        par 
            Cart Service->>Cart Cache: Pull data from Cache
            Cart Cache->>Cart Service: Pull data from Cache
        end
    Cart Service->>UI: Items returned
    end
```


```mermaid
sequenceDiagram
    par 
        Phase 1->>Phase 2: Time
    and
        Phase 1->>Phase 3: Evidence
    and 
        Phase 1->>Phase 3: Fetch items in cart
        par 
            Phase 3->>Phase 4: Pull data from Cache
            Phase 4->>Phase 3: Pull data from Cache
        end
        Phase 3->>Phase 1: Items returned
    end
```
