# Drupal Issue Queue Management

## Old

```mermaid
flowchart LR
    %% Define Global Styles
    classDef phaseBox fill:#1e1b15,stroke:#D69E2E,stroke-width:2px,color:#F6AD55,font-size:12px,font-weight:bold,rx:5px,ry:5px;
    classDef phaseBoxCyan fill:#13252a,stroke:#319795,stroke-width:2px,color:#4FD1C5,font-size:12px,font-weight:bold,rx:5px,ry:5px;
    classDef phaseBoxGreen fill:#14241d,stroke:#38A169,stroke-width:2px,color:#68D391,font-size:12px,font-weight:bold,rx:5px,ry:5px;

    %% ROW 1 (Setup Workspace): Left-to-Right Horizontal Group
    subgraph Row1 [Step 1: Setup Workspace]
        direction LR
        Node1["[Find Issue in Queue]<br/>(Review 20-200 Comments)"]:::phaseBox
        Node2["[Local Stack Setup]<br/>(DDEV/Apache/PHP)"]:::phaseBoxCyan
        Node3["[Steps to Reproduce]<br/>(Content, Fields, Roles)"]:::phaseBoxGreen

        Node1 -->|1. Validate Bug| Node2
        Node2 -->|2. Build Base| Node3
    end

    %% Step down transition between Row 1 and Row 2
    Node3 ==>|3. Establish Preconditions| Node4

    %% ROW 2 (Evaluation): Right-to-Left Horizontal Group (reverted to maintain loop)
    subgraph Row2 [Step 2: Evaluation]
        direction RL
        Node6["[Issue Queue Feedback]<br/>(RTBC / Needs Work)"]:::phaseBox
        Node5["[Manual Comparison]<br/>(Dual Browsers)"]:::phaseBoxCyan
        Node4["[Install With Patch (or MR)]<br/>(Git apply / Drush)"]:::phaseBoxGreen

        Node4 -->|4. Inspect Diff| Node5
        Node5 -->|5. Verify Changes| Node6
    end

    %% Visual feedback loop (Bottom Row back to Top Row)
    Node6 -.->|6. Restart Loop| Node1

    %% Styling Connections
    linkStyle 0 stroke:#D69E2E,stroke-width:2px;
    linkStyle 1 stroke:#319795,stroke-width:2px;
    linkStyle 2 stroke:#38A169,stroke-width:4px;
    linkStyle 3 stroke:#38A169,stroke-width:2px;
    linkStyle 4 stroke:#319795,stroke-width:2px;
    linkStyle 5 stroke:#D69E2E,stroke-width:2px,stroke-dasharray: 4 4;
```

## New

```mermaid
flowchart LR
    %% Define Global Styles
    classDef originBox fill:#1e293b,stroke:#0284c7,stroke-width:2px,color:#38bdf8,font-size:12px,font-weight:bold,rx:5px,ry:5px;
    classDef aiBox fill:#271c19,stroke:#d97706,stroke-width:2.5px,color:#f59e0b,font-size:12px,font-weight:bold,rx:8px,ry:8px;
    classDef recipeBox fill:#064e3b,stroke:#059669,stroke-width:2px,color:#34d399,font-size:11px,font-weight:bold,rx:5px,ry:5px;
    classDef envBox fill:#172554,stroke:#2563eb,stroke-width:2px,color:#60a5fa,font-size:11px,font-weight:bold,rx:5px,ry:5px;
    classDef targetBox fill:#062f4f,stroke:#06b6d4,stroke-width:2.5px,color:#22d3ee,font-size:11.5px,font-weight:bold,rx:10px,ry:10px;

    %% Row 1 (Input & AI): Wide Row
    subgraph Row1 [Step 1: Raw Queue Data & AI Triage]
        direction LR
        QueueNode["[Find Issue in Queue]<br/>(Ticket & Activity Hub)"]:::originBox
        AINode["🧠 AI Distills 'Steps' & Test Briefs<br/>(Extracts context & plans execution)"]:::aiBox

        QueueNode -->|Ingest Thread| AINode
    end

    %% Transition down
    AINode ==>|Triggers| RecipeNode
    AINode ==>|Initializes| ContainerNode

    %% Row 2 (Preparation & Verification): Horizontal, wider layout
    subgraph Row2 [Step 2: Automated Preparation & Visual Verification]
        direction LR
        RecipeNode["📄 Drupal Recipe Preconditions<br/>(Auto-applied YAML config)"]:::recipeBox
        ContainerNode["☁️ Coder + DDEV Cloud Instances<br/>(Booted 'Before' vs 'After' containers)"]:::envBox
        ViewerNode["🖥️ [Central Compare Viewer (drupal-compare)]<br/>• Side-by-Side / Onion Skin / DOM Diffing<br/>• Automated Playwright & axe-core Audits<br/>• Real-time Screen Reader & Focus Traps"]:::targetBox

        %% Ensure parallel horizontal paths pointing to the target on the right
        RecipeNode -->|Applies Config| ViewerNode
        ContainerNode -->|Orchestrates Env| ViewerNode
    end

    %% Connection styles
    linkStyle 0 stroke:#0284c7,stroke-width:2.5px;
    linkStyle 1 stroke:#d97706,stroke-width:3px,stroke-dasharray:3 3;
    linkStyle 2 stroke:#d97706,stroke-width:3px,stroke-dasharray:3 3;
    linkStyle 3 stroke:#059669,stroke-width:2px;
    linkStyle 4 stroke:#2563eb,stroke-width:2px;
```
