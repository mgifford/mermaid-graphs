# Experimenting with big government data

## Proposed Crawl Workflow

```mermaid
graph TD
    DomainList-->CrawlAndScan;
    CrawlAndScan-->ScanWithAxe;
    ScanWithAxe-->AggregateData;
    CrawlAndScan-->SanWithPlainLanguage;
    SanWithPlainLanguage-->AggregateData;
    AggregateData-->PushToBigQuery;
    PushToBigQuery-->DisplayChartsAndResults;
    DisplayChartsAndResults-->ExportToHTML;
```

## Proposed Client Workflow 

```mermaid
graph TD
   DisplayChartsAndResults-->FindDomain;
   FindDomain-->SeeChangeOverTime
   SeeChangeOverTime-->SeeDashboard
   SeeDashboard-->DigDownToTopIssues;
   DigDownToTopIssues-->ExportToHTML;
```
