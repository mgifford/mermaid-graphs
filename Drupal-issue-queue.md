# Drupal Issue Queue Management

## Old

```mermaid
flowchart TB
    accTitle: Reviewing a Drupal core issue by hand
    accDescr: A reviewer reads the issue, sets up a site and its preconditions by hand, and reproduces the bug. They apply the change, compare the two versions by eye, and report on the issue. A new version of the merge request starts the loop again. Tests and code checks already run in CI, and disposable test sites already exist.

    classDef manual fill:#1e1b15,stroke:#D69E2E,stroke-width:2px,color:#F6AD55,font-size:12px,font-weight:bold;
    classDef auto fill:#13252a,stroke:#319795,stroke-width:2px,color:#4FD1C5,font-size:12px,font-weight:bold;

    subgraph Setup [Step 1: Set up by hand]
        direction LR
        A["Read the issue<br/>(dozens to hundreds of comments,<br/>related issues, MR reviews)"]:::manual
        B["Set up a site<br/>(DDEV, or Apache,<br/>PHP and a database)"]:::manual
        C["Build the preconditions<br/>(content, fields,<br/>roles, settings)"]:::manual
        D["Reproduce the bug<br/>(core without the change)"]:::manual
        A -->|1. find the steps| B
        B -->|2. install core| C
        C -->|3. follow the steps| D
    end

    subgraph Evaluate [Step 2: Evaluate by hand]
        direction LR
        E["Apply the change<br/>(git apply a patch, or check<br/>out the issue fork branch)"]:::manual
        F["Compare by eye<br/>(two sites, or one after the other;<br/>keyboard and screen reader by hand)"]:::manual
        G["Report on the issue<br/>(Needs work, or RTBC)"]:::manual
        R["New MR version?<br/>Set it all up again<br/>from step 1"]:::manual
        E -->|5. repeat the steps| F
        F -->|6. comment| G
        G -.->|7. later| R
    end

    subgraph Automated [Already automated for years]
        direction LR
        CI["Tests and code checks run in CI<br/>on every merge request;<br/>results show on the MR"]:::auto
        SB["Disposable test sites<br/>(simplytest.me, DrupalPod)<br/>can replace setting up a site"]:::auto
    end

    Setup ==>|4. bug confirmed| Evaluate
    Evaluate ~~~ Automated
```

## New

```mermaid
flowchart TB
    accTitle: Reviewing a Drupal core issue with drupal-core-lab
    accDescr: A script writes a brief of the issue without a model. An AI assistant drafts an issue pack, a validator checks its form, and a person reads it. A person runs one command, which builds Before and After from the same core commit and the same Drupal recipe, locally or in a DDEV Coder workspace. A person compares them in the viewer while scripts record evidence. AI helps draft the write-up, and a person reviews it and posts to drupal.org. A new merge request version is rebuilt with the same command.

    classDef script fill:#172554,stroke:#2563eb,stroke-width:2px,color:#93c5fd,font-size:12px,font-weight:bold;
    classDef ai fill:#271c19,stroke:#d97706,stroke-width:2px,color:#fbbf24,font-size:12px,font-weight:bold;
    classDef person fill:#064e3b,stroke:#10b981,stroke-width:3px,color:#a7f3d0,font-size:12px,font-weight:bold;

    subgraph Understand [Step 1: Understand the issue]
        direction LR
        A["Script: issue brief<br/>(issue, related issues, MR reviews;<br/>no model, quotes word for word)"]:::script
        B["AI: drafts an issue pack<br/>(summary with sources, setup,<br/>steps, checks, questions)"]:::ai
        C["Script: validator<br/>(checks the pack's form)"]:::script
        D["Person: reads the pack<br/>(its sources and<br/>unverified list)"]:::person
        A --> B --> C --> D
    end

    subgraph Build [Step 2: Build Before and After]
        direction LR
        E["Person: runs one command<br/>node scripts/test-mr.mjs 3619154"]:::person
        F["Script: same core commit and<br/>same Drupal recipe on both sites<br/>(DDEV locally, or DDEV Coder)"]:::script
        E --> F
    end

    subgraph Compare [Step 3: Compare and report]
        direction LR
        G["Person: compares in the viewer<br/>(side by side, onion skin,<br/>difference; keyboard pass)"]:::person
        H["Script: records evidence<br/>(Playwright with real input,<br/>axe-core, accessibility tree<br/>and speech diff)"]:::script
        I["AI: helps draft the write-up<br/>(evidence, comment, Gherkin<br/>summary; each marked DRAFT)"]:::ai
        J["Person: reviews and posts<br/>to drupal.org,<br/>with AI disclosure"]:::person
        K["New MR version?<br/>The same command rebuilds;<br/>older runs are marked stale"]:::script
        G --> I
        H --> I
        I --> J
        J -.->|later| K
    end

    Understand ==>|pack is right| Build
    Build ==>|sites running| Compare
```
