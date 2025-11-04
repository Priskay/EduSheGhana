Technical Summary

 Power Query Transformations
Step	Description
1	Imported main dataset (defactopopn_10%_20221011d.csv)
2	Promoted first row as headers
3	Renamed coded columns (p02 → Age, a11d → Sex, p11a → Literacy, etc.)
4	Removed unnecessary identifiers (nqid, distcode, etc.)
5	Filtered rows: kept only ages 6–70
6	Replaced “Not Stated” and blank literacy values with nulls
7	Created Literacy_Status column using conditional logic: if [Literacy] = "Yes, read and write" or 							[Literacy] = "Yes, read only" then "Literate" else "Illiterate"	
8	Cleaned and standardized region names to match shapefile
9	Removed duplicates and confirmed data types
10	Loaded the cleaned dataset into Power BI model


Data Model

Component				Description

Fact Table			Cleaned PHC 2021 dataset (individual-level literacy records)
Dimension Table			Ghana Shapefile (region boundaries and metadata)
Key Relationship		Region ↔ Region (Many-to-One)
Cross Filter Direction		Single
Cardinality			Many-to-One (PHC → Regions)

🧠
 DAX Measures Created
Measure					Purpose
Overall Literacy Rate		Total Literate ÷ Total Respondents
Male Literacy Rate		Literate males ÷ Total males
Female Literacy Rate		Literate females ÷ Total females
Literacy Gap	Male 		Literacy Rate – Female Literacy Rate
Urban Literacy Rate		Literate respondents in Urban areas ÷ Total Urban respondents
Rural Literacy Rate		Literate respondents in Rural areas ÷ Total Rural respondents
Regional Literacy Rate		Average literacy rate per region
School Attendance Rate		Currently attending school ÷ Total respondents aged 6–25

🎨 Dashboard Layout
Page					Description
1. National Overview		Key metrics and visual summary of literacy trends across Ghana
2. Gender Insights		Male vs Female literacy comparisons and literacy gap analysis
3. Regional Insights		Choropleth map visualizing literacy by region using shapefile
4. HomePage(Info)		Project description, data sources, and recommendations


📤 Deployment Workflow

Published report to Power BI Service

Enabled navigation buttons for inter-page transitions

Adjusted formatting for presentation mode (7-min story flow)

Shared Publish-to-Web link for public access

Embedded dashboard link in GitHub and portfolio site



✅ Result

A clean, automated, and replicable data pipeline that:

Transforms raw census data into actionable insights

Uses geospatial and gender-based analysis

Enables interactive, policy-driven storytelling through Power BI