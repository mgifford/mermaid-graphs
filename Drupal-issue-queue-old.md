```mermaid
flowchart TD
    %% Define Global Styles
    classDef mainTitle fill:#121820,stroke:#2C5282,stroke-width:2px,color:#E2E8F0,font-size:18px,font-weight:bold,padding:12px;
    classDef phaseBox fill:#1e1b15,stroke:#D69E2E,stroke-width:2px,color:#F6AD55,font-size:13px,font-weight:bold,rx:5px,ry:5px;
    classDef phaseBoxCyan fill:#13252a,stroke:#319795,stroke-width:2px,color:#4FD1C5,font-size:13px,font-weight:bold,rx:5px,ry:5px;
    classDef phaseBoxGreen fill:#14241d,stroke:#38A169,stroke-width:2px,color:#68D391,font-size:13px,font-weight:bold,rx:5px,ry:5px;
    
    %% Main Header Node
    Title[THE HISTORIC TESTING LOOP]:::mainTitle

    %% Create Nodes (Rows 1 & 2)
    Node1["[Issue Queue Thread] <br/> (80+ comments)"]:::phaseBox
    Node2["[Local Stack Setup] <br/> (DDEV/Apache/PHP)"]:::phaseBoxCyan
    Node3["[Manual Recipe/Setup] <br/> (Content, Fields, Roles)"]:::phaseBoxGreen
    Node4["[Apply Patch & Re-install] <br/> (Git apply / Drush)"]:::phaseBoxGreen
    Node5["[Manual Comparison] <br/> (Dual Browsers)"]:::phaseBoxCyan
    Node6["[Issue Queue Feedback] <br/> (RTBC / Needs Work)"]:::phaseBox

    %% Position Title & Connect Nodes
    Title -.-> Node1
    
    Node1 -->|1. Locate Patch| Node2
    Node2 -->|2. Build Base Env| Node3
    Node3 -->|3. Establish Preconditions| Node4
    Node4 -->|4. Inspect Differences| Node5
    Node5 -->|5. Verify Changes| Node6
    Node6 -.->|Restart Loop| Node1

    %% Subgraph layout tricks to retain top-to-bottom matrix row alignment
    subgraph Row1 [Step 1: Setup Workspace]
        direction LR
        Node1
        Node2
        Node3
    end

    subgraph Row2 [Step 2: Evaluation]
        direction RL
        Node4
        Node5
        Node6
    end

    %% Flow connector between the rows
    Node3 ====> Node4
    
    %% Styling Connections
    linkStyle 1 stroke:#D69E2E,stroke-width:2px,color:#D69E2E;
    linkStyle 2 stroke:#319795,stroke-width:2px,color:#319795;
    linkStyle 3 stroke:#38A169,stroke-width:2px,color:#38A169;
    linkStyle 4 stroke:#38A169,stroke-width:2px,color:#38A169;
    linkStyle 5 stroke:#319795,stroke-width:2px,color:#319795;
    linkStyle 6 stroke:#D69E2E,stroke-width:2px,color:#D69E2E,stroke-dasharray: 5 5;
```
