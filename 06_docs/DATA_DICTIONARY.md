# Data Dictionary

## Project

Boundary Ridge Mining Fleet Reliability and Maintenance Performance

## Purpose

This data dictionary explains the main datasets, key fields, quality flags and reporting logic used in the Boundary Ridge Mining fleet reliability portfolio project.

The dataset is simulated for portfolio and learning purposes. Boundary Ridge Mining is fictional and does not represent a real company, mine site or ASX-listed entity.

## Dataset Overview

| Table | Description | Main reporting use |
|---|---|---|
| asset_register | Master list of fleet assets | Asset names, classes, criticality and status |
| breakdown_events | Breakdown incidents and downtime events | Breakdown frequency and downtime analysis |
| crew_roster | Crew and shift roster information | Shift context, absenteeism and overtime |
| fuel_usage | Fuel consumption and operating-hour records | Fuel usage, operating hours and fuel data quality |
| maintenance_work_orders | Preventive and corrective maintenance records | Maintenance workload, cost, failure categories and downtime |
| parts_inventory | Parts, suppliers and delivery information | Inventory, stockout and delivery delay context |
| shift_operations_log | Shift-level operating performance records | Operating hours, downtime and production context |
| DimDate | Calendar table created in Power BI | Date filtering, month, quarter and year reporting |
| _Measures | Power BI measure table | Stores DAX measures used across report pages |

## Key Tables and Fields

### asset_register

| Field | Description |
|---|---|
| asset_id | Unique asset identifier used to connect fleet records |
| asset_name | Readable asset name used in report visuals |
| asset_class | Fleet category, such as Haul Truck, Excavator, Drill Rig, Wheel Loader, Light Vehicle or Water Cart |
| criticality_rating | Operational criticality of the asset |
| manufacturer | Asset manufacturer |
| model | Asset model |
| status | Asset status, such as active or inactive |

### breakdown_events

| Field | Description |
|---|---|
| breakdown_id | Unique breakdown event identifier |
| asset_id | Asset linked to the breakdown event |
| event_start | Breakdown start date/time |
| event_end | Breakdown end date/time |
| downtime_hours | Duration of the breakdown |
| failure_category | Failure category recorded in the source data |
| failure_description | Description of the breakdown event |

### maintenance_work_orders

| Field | Description |
|---|---|
| work_order_id | Work order identifier from the source data |
| asset_id | Asset linked to the work order |
| date_raised | Date the work order was raised |
| planned_start_date | Planned work start date |
| actual_start_date | Actual work start date |
| actual_finish_date | Actual work finish date |
| work_order_type | Preventive or corrective maintenance type |
| status | Work order status |
| failure_code | Source failure code |
| failure_description | Description of maintenance issue |
| priority | Work order priority |
| labour_hours | Labour hours recorded against the work order |
| materials_cost_aud | Materials cost in Australian dollars |
| external_service_cost_aud | External service cost in Australian dollars |
| downtime_hours | Downtime linked to the work order |
| Failure_Category_Standardised | Cleaned and standardised failure category |
| Work_Order_Quality_Flag | Data-quality flag applied during cleaning |
| Include_In_Work_Order_Analysis | Indicates whether the work order is included in Power BI KPI analysis |

### fuel_usage

| Field | Description |
|---|---|
| asset_id | Source asset identifier |
| Asset_ID_Standardised | Cleaned asset identifier used for matching |
| date | Fuel record date |
| fuel_litres | Fuel consumed |
| operating_hours | Operating hours recorded |
| Fuel_Record_Quality_Flag | Data-quality flag applied to the fuel record |
| Include_In_Fuel_Analysis | Indicates whether the record is included in fuel KPI analysis |

### shift_operations_log

| Field | Description |
|---|---|
| asset_id | Source asset identifier |
| Asset_ID_Standardised | Cleaned asset identifier used for matching |
| date | Shift date |
| shift | Shift identifier |
| operating_hours | Operating hours for the shift |
| downtime_hours | Downtime hours for the shift |
| production_tonnes | Production output where applicable |
| Asset_Match_Flag | Indicates whether the asset matched to the asset register |
| Shift_Log_Quality_Flag | Data-quality flag applied to the shift record |
| Include_In_Shift_Analysis | Indicates whether the shift record is included in KPI analysis |

### crew_roster

| Field | Description |
|---|---|
| date | Roster date |
| shift | Shift identifier |
| crew_id | Crew identifier |
| planned_headcount | Planned number of people rostered |
| actual_headcount | Actual number of people present |
| absenteeism_count | Number of absent workers |
| overtime_hours | Overtime hours recorded |

### parts_inventory

| Field | Description |
|---|---|
| part_id | Unique part identifier |
| part_name | Name of the part |
| asset_class | Asset class associated with the part |
| supplier_name | Supplier name |
| current_stock | Current stock level |
| reorder_point | Stock level that triggers reorder |
| order_date | Date the part was ordered |
| expected_delivery_date | Expected delivery date |
| actual_delivery_date | Actual delivery date |
| stockout_flag | Indicates whether a stockout occurred |

## Data Quality Fields

| Field | Table | Purpose |
|---|---|---|
| Work_Order_Quality_Flag | maintenance_work_orders | Flags work orders with valid, missing, duplicate or invalid values |
| Include_In_Work_Order_Analysis | maintenance_work_orders | Controls whether work orders are included in KPI calculations |
| Fuel_Record_Quality_Flag | fuel_usage | Flags missing fuel litres or invalid fuel records |
| Include_In_Fuel_Analysis | fuel_usage | Controls whether fuel records are included in fuel analysis |
| Shift_Log_Quality_Flag | shift_operations_log | Flags invalid operating or downtime hour records |
| Asset_Match_Flag | shift_operations_log | Shows whether the asset could be matched to the asset register |
| Include_In_Shift_Analysis | shift_operations_log | Controls whether shift records are included in operational KPI calculations |

## Reporting Notes

The Power BI report separates raw record counts from valid analytical records.

Records with data-quality issues are not silently deleted. They are flagged and excluded only where they would make a KPI unreliable.

The Data Quality Audit page summarises exclusion counts and inclusion rates so report users can understand the confidence level behind the analysis.

## DAX Measures

DAX measures are documented separately in:

`DAX_Measure_Dictionary.docx`

This data dictionary focuses on source tables, key fields and data-quality logic.