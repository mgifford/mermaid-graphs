# Drupal Issue Queue Management

## Old

```mermaid
flowchart TD
    %% Define Global Styles
    classDef phaseBox fill:#1e1b15,stroke:#D69E2E,stroke-width:2px,color:#F6AD55,font-size:12px,font-weight:bold,rx:5px,ry:5px;
    classDef phaseBoxCyan fill:#13252a,stroke:#319795,stroke-width:2px,color:#4FD1C5,font-size:12px,font-weight:bold,rx:5px,ry:5px;
    classDef phaseBoxGreen fill:#14241d,stroke:#38A169,stroke-width:2px,color:#68D391,font-size:12px,font-weight:bold,rx:5px,ry:5px;

    %% Row 1 Setup: Define placement & connect L-to-R
    Node1["[Issue Queue Thread]<br/>(80+ comments)"]:::phaseBox
    Node2["[Local Stack Setup]<br/>(DDEV/Apache/PHP)"]:::phaseBoxCyan
    Node3["[Manual Recipe/Setup]<br/>(Content, Fields, Roles)"]:::phaseBoxGreen
    
    Node1 -->|1. Locate Patch| Node2
    Node2 -->|2. Build Base| Node3

    %% Row 2 Setup: Define placement & connect R-to-L
    Node4["[Apply Patch & Re-install]<br/>(Git apply / Drush)"]:::phaseBoxGreen
    Node5["[Manual Comparison]<br/>(Dual Browsers)"]:::phaseBoxCyan
    Node6["[Issue Queue Feedback]<br/>(RTBC / Needs Work)"]:::phaseBox

    Node4 -->|4. Inspect Diff| Node5
    Node5 -->|5. Verify Changes| Node6

    %% Cascading vertical connect between Row 1 and Row 2
    Node3 -->|3. Establish Preconditions| Node4

    %% Visual feedback loop (Bottom left to top left)
    Node6 -.->|6. Restart Loop| Node1

    %% Align Row 1 and Row 2 horizontally side-by-side using group alignments
    subgraph Row1 [Setup Workspace (Top Row)]
        direction LR
        Node1
        Node2
        Node3
    end

    subgraph Row2 [Manual Evaluation (Bottom Row)]
        direction RL
        Node4
        Node5
        Node6
    end

    %% Style connection routes manually
    linkStyle 0 stroke:#D69E2E,stroke-width:2px;
    linkStyle 1 stroke:#319795,stroke-width:2px;
    linkStyle 2 stroke:#38A169,stroke-width:2px;
    linkStyle 3 stroke:#38A169,stroke-width:2px;
    linkStyle 4 stroke:#319795,stroke-width:2px;
    linkStyle 5 stroke:#D69E2E,stroke-width:2px,stroke-dasharray: 4 4;
```

## New

```mermaid
flowchart TD
    %% Define Global Styles
    classDef originBox fill:#1e293b,stroke:#0284c7,stroke-width:2px,color:#38bdf8,font-size:12px,font-weight:bold,rx:5px,ry:5px;
    classDef aiBox fill:#271c19,stroke:#d97706,stroke-width:2.5px,color:#f59e0b,font-size:12px,font-weight:bold,rx:8px,ry:8px;
    classDef recipeBox fill:#064e3b,stroke:#059669,stroke-width:2px,color:#34d399,font-size:11px,font-weight:bold,rx:5px,ry:5px;
    classDef envBox fill:#172554,stroke:#2563eb,stroke-width:2px,color:#60a5fa,font-size:11px,font-weight:bold,rx:5px,ry:5px;
    classDef targetBox fill:#062f4f,stroke:#06b6d4,stroke-width:2.5px,color:#22d3ee,font-size:11.5px,font-weight:bold,rx:10px,ry:10px;

    %% Row 1 Elements: Inputs & Intelligence 
    QueueNode["[Drupal.org Issue Queue]<br/>(Ticket & Activity Hub)"]:::originBox
    AINode["🧠 AI Distills 'Steps' & Test Briefs<br/>(Extracts context & plans execution)"]:::aiBox

    %% Row 2 Elements: Tasks & Final Viewer
    RecipeNode["📄 Drupal Recipe Preconditions<br/>(Auto-applied YAML config)"]:::recipeBox
    ContainerNode["☁️ Coder + DDEV Cloud Instances<br/>(Booted 'Before' vs 'After' containers)"]:::envBox
    ViewerNode["🖥️ [Central Compare Viewer (drupal-compare)]<br/>• Side-by-Side / Onion Skin / DOM Diffing<br/>• Automated Playwright & axe-core Audits<br/>• Real-time Screen Reader & Focus Traps"]:::targetBox

    %% Row 1 connections
    QueueNode -->|Ingest Thread| AINode

    %% Vertical down-connections directly from the processing row (Row 1)
    AINode -->|1. Generate Blueprint| RecipeNode
    AINode -->|2. Provision Specs| ContainerNode

    %% Concluding connections merging into Viewer in Row 2
    RecipeNode -->|Applies Config| ViewerNode
    ContainerNode -->|Orchestrates Env| ViewerNode

    %% Enforced dual-row stacking grouping 
    subgraph InputRow [Phase 1: Raw Queue Data & AI Triage]
        direction LR
        QueueNode
        AINode
    end

    subgraph ExecutionRow [Phase 2: Automated Preparation & Visual Verification]
        direction LR
        RecipeNode
        ContainerNode
        ViewerNode
    end

    %% Apply visual styling pathways
    linkStyle 0 stroke:#0284c7,stroke-width:2.5px;
    linkStyle 1 stroke:#d97706,stroke-width:2px,stroke-dasharray:3 3;
    linkStyle 2 stroke:#d97706,stroke-width:2px,stroke-dasharray:3 3;
    linkStyle 3 stroke:#059669,stroke-width:2px;
    linkStyle 4 stroke:#2563eb,stroke-width:2px;
```
