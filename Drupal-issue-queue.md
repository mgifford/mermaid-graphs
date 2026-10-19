# Drupal Issue Queue Management

## Old

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
    linkStyle 1 stroke:#D69E2E,stroke-width:2px;
    linkStyle 2 stroke:#319795,stroke-width:2px;
    linkStyle 3 stroke:#38A169,stroke-width:2px;
    linkStyle 4 stroke:#38A169,stroke-width:2px;
    linkStyle 5 stroke:#319795,stroke-width:2px;
    linkStyle 6 stroke:#D69E2E,stroke-width:2px,stroke-dasharray:5 5;
```

## New

```mermaid
flowchart TD
    %% Define Global Styles
    classDef title fill:#0f172a,stroke:#0ea5e9,stroke-width:2px,color:#38bdf8,font-size:18px,font-weight:bold,padding:12px;
    classDef originBox fill:#1e293b,stroke:#0284c7,stroke-width:2px,color:#38bdf8,font-weight:bold;
    classDef aiBox fill:#271c19,stroke:#d97706,stroke-width:2.5px,color:#f59e0b,font-weight:bold,rx:8px,ry:8px;
    classDef recipeBox fill:#064e3b,stroke:#059669,stroke-width:2px,color:#34d399,font-weight:bold;
    classDef envBox fill:#172554,stroke:#2563eb,stroke-width:2px,color:#60a5fa,font-weight:bold;
    classDef targetBox fill:#062f4f,stroke:#06b6d4,stroke-width:3px,color:#22d3ee,font-size:14px,font-weight:bold,rx:10px,ry:10px;

    %% Headline Title
    Title[THE CLOUD TESTING PARADIGM]:::title

    %% Node Structures
    StartNode["[Drupal.org Issue Queue] <br/> (Ticket & Activity Hub)"]:::originBox
    AINode["🧠 AI Distills 'Steps to Reproduce' & Test Briefs <br/> (Analyzes threads, parses requirements & builds briefs)"]:::aiBox
    RecipeNode["📄 Drupal Recipe Automatically <br/> Provisions Exact Preconditions <br/> (Applies YAML blueprints: Content, Fields, Roles)"]:::recipeBox
    ContainerNode["☁️ Coder + DDEV Boots <br/> Dual Cloud Instances (Before & After) <br/> (Stateless, on-demand test environments)"]:::envBox
    ViewerNode["🖥️ [Central Compare Viewer (drupal-compare)] <br/> • Side-by-Side / Onion Skin / DOM Diffing <br/> • Automated Playwright & axe-core Audits <br/> • Real-time Screen Reader & Focus Traps"]:::targetBox

    %% Sequence flow and logic
    Title -.-> StartNode
    StartNode -->|Ingest Thread| AINode
    
    %% AI driving the processes
    AINode -->|Inject Requirements| RecipeNode
    AINode -->|Initialize Specs| ContainerNode
    
    %% Execution down to viewer
    RecipeNode -->|Applies Config State| ViewerNode
    ContainerNode -->|Orchestrates Environment| ViewerNode

    %% Styling lines with tech accents 
    linkStyle 1 stroke:#0284c7,stroke-width:2.5px;
    linkStyle 2 stroke:#d97706,stroke-width:2.5px,stroke-dasharray:3 3;
    linkStyle 3 stroke:#d97706,stroke-width:2.5px,stroke-dasharray:3 3;
    linkStyle 4 stroke:#059669,stroke-width:2px;
    linkStyle 5 stroke:#2563eb,stroke-width:2px;
```
