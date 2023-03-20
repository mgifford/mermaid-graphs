# Experimenting with big government data

## Proposed Crawl Workflow

```mermaid
graph TD
    DomainList-->Crawl4URLs;
    Crawl4URLs[Crawl with ??]-->DumpToMySQL;
    DumpToMySQL-->ScanWithAxe;
    ScanWithAxe-->DumpToMySQL;
    DumpToMySQL-->SanWithPlainLanguage;
    SanWithPlainLanguage-->DumpToMySQL;
    DumpToMySQL-->AggregateData;
    AggregateData-->PushToGoogleSheets;
    PushToGoogleSheets-->DisplayChartsAndResults;
    DisplayChartsAndResults-->ExportToHTML;
```

## Proposed Client Workflow 

```mermaid
graph TD
   GotoGoogleSheet-->FindDomain;
   FindDomain-->SeeChangeOverTime
   SeeChangeOverTime-->SeeDashboard
   SeeDashboard-->DigDownToTopIssues;
   DigDownToTopIssues-->ExportToHTML;
```
