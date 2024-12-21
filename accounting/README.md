# Accounting company, data from Customers - Income analysis

![Accounting report](accounting\images\accounting_report_header.png)

Tools:
- basics: MS Excel
- advanced: MS PowerBI

## Excel - data quality check

Analyzing an accounting dataset in MS Excel involves several key steps to extract meaningful insights. In this case, data quality was checked to ensure accuracy by verifying completeness, consistency, type and typing errors, and removing any duplicate (redundancy) or irrelevant entries.

Basic analyses are included as calculating totals for revenue, expenses, and net profit using simple formulas. Pivot tables are used to group and summarize financial data, such as categorizing transactions by date, Client. 

![Basic pivot plot](images\Report_Excel_SelectedUserIncome_YQuarters_styled.png)

Additionally, charts like bar graphs and pie charts could have provided visual overview of key financial metrics, making it easier to identify trends or areas of concern, ... but it was made in PowerBI, because it is a better tool for such analysis.

## MS Power BI report

A 2-in-1 PowerBI report: the first dashboards - called insights - are analysing Clients of the Accounting company, in general for filings, sum revenue and expenses, outlier detection, currencies, currency conversion to EUR...
Second part is a real report for Customers as Clients, summarizing year trends, revenue and expenses amounts, cashflow.
Both part contains visualizations and tables/matrices in static and in interactive format.
Countries – Country codes match check, UserID – UserName match check

### ETL, Data Analysis – Understanding data
The excel file (xlsx) containing the data was loaded and transformed (correcting typo and date format errors), then measures were calculated, further dimension tables were added for better performance and to match standards.

1)	Values / (min/max) ranges in each column
Null value (string), mistyped values (Country code)
2)	Date format error correction
3)	Redundant columns check (there are 2 pairs)

The created __insight pages__ are for Accounting company internal use to validate overall income values, filings compliances, workload periodicity, outlier values detection, …
Reports pages are made for Clients to validate their revenue position.
From a technical viewpoint visuals, tables, matrices, field parameters, and different types of filters (value-based, textual, graphical), conditional formatting were used.
I made a global report for all stakeholders but in a real case either Customers or internal colleagues would be targeted and report would contain only specific content. Minimal explanation is provided as information should be presented and explained orally.

### Development options
A major part of _Data Table Normalisation_ was done but it could be further optimised for example introducing a Countries_dim table. Dates table is present but it is somehow incompatible with the given dates.

Further cleaning of column names (in tables) for easier and cleaner data. 

Performance boosting. Performance test were done, see images in _optimization_ folder.

From GDPR/PI viewpoint *Roles* may be introduced for each Client to be restricted to view only their own data.

### Further notes
Data anomalies to validate

In some cases data validity should be verified with DataEngineers/data providers
1)	Zero income all times
2)	Outlier VAT values
Is it normal / forgotten data filings / missing or unprecise data?

1)	This could be valid, but I consider that it should be verified with Accountants / data preparing colleagues.
2)	Extreme outliers may make plotting complicated. Log-lin (income vs time) scaled plotting could resolve this situtation in visualization but it depends on the company whether it is an accepted solution.
