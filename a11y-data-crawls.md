# Experimenting with big government data


## Research Workflow
```mermaid
graph TD
    DomainList-->Crawl4URLs;
    Crawl4URLs[Crawl with ??]-->DumpToMySQL;
    ScanWithAxe-->ScanWithAxe;
    ScanWithAxe-->DumpToMySQL;
    DumpToMySQL-->AggregateData;
    AggregateData-->PushToGoogleSheets;
    PushToGoogleSheets-->DisplayChartsAndResults;
    DisplayChartsAndResults-->ExportToHTML;
```