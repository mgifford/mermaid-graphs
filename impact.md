# Impact Direction for Sales

## Proposed Crawl Workflow

```mermaid
graph TD
    CheckAgency-->IsGreen{{Is Green}};
    IsGreen-->AgencyColor;
    AgencyColor-->GreenAgency;
    AgencyColor-->AmberAgency;
    AgencyColor--> RedAgency;
    RedAgency-->GreenProject;
    AmberAgency-->GreenProject;
    RedProject-->GreenProject;
    RedProject-->No;
    GreenProject-->Yes;


```

## Ignore

```mermaid
graph TD
   GotoGoogleSheet-->FindDomain;
   FindDomain-->SeeChangeOverTime
   SeeChangeOverTime-->SeeDashboard
   SeeDashboard-->DigDownToTopIssues;
   DigDownToTopIssues-->ExportToHTML;
```
