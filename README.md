# Boundary Ridge Mining Fleet Reliability and Maintenance Performance

## Project Overview

An end-to-end data analytics portfolio project focused on fleet reliability, maintenance performance, operational downtime, data quality and supply-chain delays within a simulated mining operation.

Boundary Ridge Mining is a fictional mining operation created for a simulated portfolio dataset. It is not intended to represent any real company, mine site or ASX-listed entity.

The dataset is a realistic simulated mining fleet dataset designed to reproduce common maintenance, operational, inventory and data-quality challenges.

## Business Problem

Boundary Ridge Mining manages a 35-asset mobile fleet operating across two 12-hour shifts. Operations leadership needs a clear view of repeat failures, downtime drivers, maintenance cost, data-quality issues and assets requiring maintenance intervention or replacement planning.

The business needs to answer:

- Which assets are driving the most downtime?
- Which failure categories appear most often?
- Which assets have the highest maintenance cost?
- How reliable is the underlying operational and maintenance data?
- Which records were excluded from analysis because of data-quality rules?
- What maintenance and reporting actions should leadership prioritise?

## Project Objectives

- Identify assets with the highest downtime and breakdown frequency.
- Analyse recurring failure categories across the fleet.
- Review maintenance cost and work order patterns.
- Assess operational, fuel and work order data quality before drawing conclusions.
- Build a Power BI report that supports executive decision-making.
- Document the cleaning, modelling, SQL, DAX and reporting process clearly enough for portfolio review.

## Tools Used

- Excel
- Power Query
- SQL Server and SQL Server Management Studio
- Power BI
- DAX
- GitHub Desktop
- Visual Studio Code

## Skills Demonstrated

- Data cleaning and transformation
- Data-quality flagging and exclusion logic
- Relational data modelling
- SQL table creation, loading and validation
- SQL analysis for reliability and maintenance performance
- DAX measure creation
- Power BI report design
- Drillthrough page design
- Bookmark-based navigation
- Dashboard accessibility and formatting consistency
- Project documentation
- GitHub version control

## Project Status

Power BI report build complete.

The project is currently in final documentation and publishing review. The remaining work focuses on data provenance, data dictionary, final insights and recommendations, README polish and final GitHub publishing checks.

## Dataset Summary

The project uses seven simulated source tables:

| Dataset | Purpose |
|---|---|
| Asset register | Fleet asset master data, including asset class, criticality and status |
| Breakdown events | Breakdown history and downtime events |
| Crew roster | Shift and crew roster information |
| Fuel usage | Fuel consumption and operating-hour records |
| Maintenance work orders | Preventive and corrective maintenance work order records |
| Parts inventory | Parts, suppliers, stock levels and delivery dates |
| Shift operations log | Shift-level operating hours, downtime and production context |

Raw source data is kept out of the public repository. The public repository contains project files, SQL scripts, documentation and screenshots only.

## Data Cleaning and Quality Approach

The project includes practical data-quality controls across key operational datasets.

Examples of issues handled include:

- Inconsistent failure category labels
- Missing or invalid work order dates
- Duplicate work order IDs
- Negative labour-hour records
- Missing fuel litres
- Malformed asset IDs
- Shift records with negative operating or downtime hours
- Asset records that could not be matched to the asset register

Quality flags and inclusion fields were created to separate records suitable for analysis from records that required exclusion or caution.

The final Power BI report includes a dedicated Data Quality and Audit page to make these controls visible.

## SQL Analysis

The SQL workflow is documented in the [`03_sql`](03_sql/) folder.

It includes:

- SQL Server database setup
- Table creation for all project datasets
- Loading all seven project tables
- Row-count validation
- Data-quality checks
- Asset reliability analysis
- Maintenance performance analysis

[View SQL scripts](03_sql/)

## Power BI Report

The Power BI report is stored in the [`04_power_bi`](04_power_bi/) folder.

The report includes the following pages:

| Page | Purpose |
|---|---|
| Executive Overview | High-level fleet reliability, downtime and maintenance performance summary |
| Measure Check | Validation page for checking DAX measures |
| Asset Reliability | Asset-level breakdown frequency, downtime exposure and maintenance risk |
| Maintenance Failure Analysis | Work order patterns, failure categories and maintenance cost drivers |
| Data Quality Audit | Excluded records, inclusion rates and reporting confidence |
| Asset Detail | Drillthrough page for selected asset-level detail |

The report also includes:

- KPI cards
- Bar charts
- Scatter analysis
- Tables
- Slicers
- Drillthrough navigation
- Bookmark-based navigation menu
- Consistent page formatting and accessibility styling

## Key Report Measures

The DAX layer includes measures for:

- Asset count
- Breakdown count
- Total downtime hours
- Downtime rate
- Maintenance cost
- Work order counts
- Excluded record counts
- Inclusion rates
- Fuel records
- Shift records
- Maintenance cost per work order
- Average downtime per asset
- Average downtime per breakdown

The measure dictionary is documented in:

[`06_docs/DAX_Measure_Dictionary.docx`](06_docs/DAX_Measure_Dictionary.docx)

## Documentation

Supporting documentation is stored in the [`06_docs`](06_docs/) folder.

Current documentation includes:

- Build log
- Data cleaning log
- Data model notes
- DAX measure dictionary
- Excel raw data audit
- Project documentation and supporting notes

Planned final documentation includes:

- Data provenance
- Practical data dictionary
- Final insights and recommendations

## Screenshots and Evidence

Portfolio screenshots are stored in the [`07_screenshots`](07_screenshots/) folder.

The screenshot evidence documents the project build process, including:

- Folder setup
- Power Query cleaning
- SQL database and scripts
- Power BI model setup
- DAX measures
- Dashboard pages
- Navigation menu
- Final report consistency pass

## Repository Structure

```text
01_raw_data/              Local source extracts, excluded from GitHub
02_cleaned_data/          Cleaned datasets and outputs
03_sql/                   SQL scripts
04_power_bi/              Power BI project files
06_docs/                  Project documentation and decision logs
07_screenshots/           Portfolio screenshots
08_screen_recordings/     Local screen recordings, excluded from GitHub
09_build_evidence/        Local behind-the-scenes build evidence, excluded from GitHub
```
## Important Repository Notes

Raw data, screen recordings and behind-the-scenes build evidence are not intended for public GitHub publishing.

The public repository is intended to show:

- The final Power BI report file
- SQL scripts
- Documentation
- Screenshots
- Project structure
- Version control history

## Current Project Phase

This project is now in the final documentation and publishing stage.

Next steps:

1. Complete `DATA_PROVENANCE.md`
2. Complete the practical data dictionary
3. Finalise insights and recommendations
4. Complete README polish
5. Run final GitHub publishing checks
6. Prepare portfolio summary and resume bullets

## Author

Rosabella Daniels

Data analytics and business intelligence portfolio focused on mining, energy, infrastructure, maintenance performance and project controls reporting.