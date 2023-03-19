# Agile Sprint

```mermaid
graph TD
      accTitle: Agile Sprint
      accDescr {
 Description of the sprint cycle.
         }

ProductOwner --> Team
Team --> Backlog
Backlog --> SprintWork
SprintWork((2 week sprints)) --> DailyScrum
DailyScrum((Daily Scrum Meeting))
SprintWork --> FinishedWork
SprintDemo[Sprint Demo + Team Retro] --> FinishedWork
```
