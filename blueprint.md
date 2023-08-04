# Service Design Visualizations in Mermaid

What can we do to simplify building simple semantic diagrams.

## Service Design Blueprint 

Can we do this in Mermaid roughly based on what I see frim this [digital template](https://www.nngroup.com/articles/service-blueprinting-template/). 

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


## Sample Customer Journey 

Just taken from the [docs](https://mermaid.js.org/syntax/userJourney.html).

```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

```mermaid
sequenceDiagram
    actor me
    participant apiSrv as control plane<br><br>api-server
    participant etcd as control plane<br><br>etcd datastore
    participant cntrlMgr as control plane<br><br>controller<br>manager
    participant sched as control plane<br><br>scheduler
    participant kubelet as node<br><br>kubelet
    participant container as node<br><br>container<br>runtime
    me->>apiSrv: 1. kubectl create -f pod.yaml
    apiSrv-->>etcd: 2. save new state
    cntrlMgr->>apiSrv: 3. check for changes
    sched->>apiSrv: 4. watch for unassigned pods(s)
    apiSrv->>sched: 5. notify about pod w nodename=" "
    sched->>apiSrv: 6. assign pod to node
    apiSrv-->>etcd: 7. save new state
    kubelet->>apiSrv: 8. look for newly assigned pod(s)
    apiSrv->>kubelet: 9. bind pod to node
    kubelet->>container: 10. start container
    kubelet->>apiSrv: 11. update pod status
    apiSrv-->>etcd: 12. save new state
```

## What else

Check out the [other examples](https://mermaid.js.org/syntax/examples.html).
