# Data Provenance

## Project

Boundary Ridge Mining Fleet Reliability and Maintenance Performance

## Dataset Status

This project uses a realistic simulated mining fleet dataset created for portfolio and learning purposes.

Boundary Ridge Mining is a fictional mining operation. It is not intended to represent any real company, mine site or ASX-listed entity.

The dataset was designed to reproduce common maintenance, operational, inventory and data-quality challenges that can appear in mining, energy and infrastructure reporting environments.

## Source Data

The project uses seven simulated CSV source files:

| Source file | Purpose | Public repository status |
|---|---|---|
| asset_register.csv | Fleet asset master data | Excluded from public GitHub |
| breakdown_events.csv | Breakdown incidents and downtime events | Excluded from public GitHub |
| crew_roster.csv | Crew staffing, absenteeism and overtime context | Excluded from public GitHub |
| fuel_usage.csv | Fuel consumption and operating-hour records | Excluded from public GitHub |
| maintenance_work_orders.csv | Preventive and corrective maintenance work orders | Excluded from public GitHub |
| parts_inventory.csv | Parts inventory, stockouts and supplier delivery timing | Excluded from public GitHub |
| shift_operations_log.csv | Shift-level operating performance and downtime records | Excluded from public GitHub |

## Public Repository Approach

Raw source data is retained locally and excluded from the public repository.

The public repository contains:

- Power BI report file
- SQL scripts
- Documentation
- Screenshots
- Project structure
- Version control history

This approach protects the raw working dataset while still showing the analytical process, modelling decisions, dashboard output and portfolio evidence.

## Data Preparation Summary

Initial data review was completed in Excel. Repeatable cleaning and transformation work was completed in Power Query.

The cleaning process included:

- Reviewing row counts and expected columns
- Checking duplicate identifiers
- Standardising inconsistent asset ID formats
- Standardising maintenance failure categories
- Converting date, time and numeric fields to suitable types
- Creating data-quality flags
- Creating inclusion and exclusion fields for reporting measures
- Retaining original source columns where useful for auditability

## Data Quality Controls

The project does not delete data-quality issues silently.

Records with issues are retained where practical, flagged, and excluded from selected KPIs only when they are not reliable for that specific analysis.

Examples include:

- Missing fuel litres retained as null and excluded from fuel-consumption KPIs
- Invalid work order dates converted to null and flagged
- Duplicate work order IDs handled using a surrogate SQL key
- Unmatched asset IDs retained for audit visibility but excluded from KPI analysis
- Negative operational hour records flagged and excluded from operational KPI measures

## Reporting Confidence

The Power BI report includes a Data Quality and Audit page showing:

- Total excluded records
- Work order inclusion rate
- Shift record inclusion rate
- Fuel record inclusion rate
- Exclusion counts by dataset

This makes reporting confidence visible to users instead of hiding data-quality limitations.

## Limitations

This is a simulated dataset and should not be used for real operational decision-making.

The analysis demonstrates a realistic analytics workflow, but the values, assets, suppliers, mine context and operational events are fictional.

## Governance Notes

The project separates:

- Raw source data
- Cleaned and modelled reporting tables
- SQL validation scripts
- DAX measures
- Dashboard visuals
- Build documentation
- Screenshot evidence

This supports traceability from source files through to final report outputs.