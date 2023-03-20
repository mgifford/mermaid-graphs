# Experimenting with big government data

## Research Workflow

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
