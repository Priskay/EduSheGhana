EduSheGhana – Data Pipeline Overview

Goal
To build a streamlined and replicable process for transforming raw census data into analytical insights and Power BI dashboards.

Pipeline Architecture
[Data Sources] 
      ↓
[Data Cleaning & Transformation] 
      ↓
[Data Modeling in Power BI]
      ↓
[DAX Measures & Visualization]
      ↓
[Interactive Dashboard & Insights]


1️⃣ Data Ingestion

Source: Ghana Statistical Service (PHC 2021, 10% Microdata).

Loaded CSV data into Power BI via Power Query.

Imported Shapefile (GeoJSON/ZIP) containing region polygons for map visualization.


2️⃣ Data Cleaning & Transformation

Executed Power Query transformations:

Renamed columns, removed irrelevant fields, filtered ages (6–70).

Created derived columns for literacy and education indicators.

Ensured consistency between regional names in census data and shapefiles.


3️⃣ Data Modeling

Established relationships:

Region (in PHC data) ↔ Region (in shapefile data)

Defined cardinality as “Many to One” (PHC → Shapefile)

Set cross-filter direction to “Single”


4️⃣ Feature Engineering (Measures in DAX)

Created key indicators:

Overall Literacy Rate

Male Literacy Rate

Female Literacy Rate

Urban vs Rural Literacy

Regional Literacy Rate

Literacy Gap (Male – Female)

School Attendance Rate

Applied formatting (Percentages, 1 Decimal Place)


5️⃣ Visualization

Designed 3 interconnected dashboards:

National Overview → Summary KPIs and literacy distribution

Gender Insights → Male vs Female literacy comparison

Regional Insights → Choropleth map using shapefiles


6️⃣ Deployment

Published Power BI report to Power BI Service.

Enabled navigation buttons for interactive exploration.

Shared public link for access and embedded it in GitHub/portfolio.


✅ Outcome

A dynamic dashboard providing:

360° view of Ghana’s literacy situation

Gender and regional disparities

Actionable insights for policymakers and educators