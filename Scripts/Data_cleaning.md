
EduSheGhana – Data Cleaning Summary

Data Sources:
2021 Population and Housing Census (PHC) Microdata (10% sample)
Ghana 16-Region Shapefiles


1️⃣ Data Import

Imported five CSV files from PHC 2021 microdata (defactopopn_10%_20221011d.csv, housingandsanitation_10%_..., etc.).

The defactopopn dataset was selected as the main source because it contained demographic and literacy-related variables.

Imported shapefiles for Ghana’s 16 regions for geospatial analysis in Power BI.


2️⃣ Data Inspection

Reviewed column names and data types using Power Query.

Identified useful variables such as:

region → Region name

a11d → Sex

p02 → Age

p11a → Literacy

p12a and p12b → School attendance and education level

urbrur → Residence type (Urban/Rural)


3️⃣ Data Cleaning Steps

Renamed columns to human-readable names:
a11d → Sex, p02 → Age, p11a → Literacy, urbrur → Residence_Type, etc.


Removed irrelevant columns such as nqid, distcode, and other identifiers not needed for analysis.


Handled missing values:

Dropped rows with nulls in key columns like region, Sex, or Literacy.

Replaced “Not Stated” in Literacy with blank values.


Filtered data:

Removed individuals younger than 6 years (since literacy and school attendance are only meaningful for age 6+).

Kept ages between 6 and 70 for analysis consistency.


Categorized Literacy:

Created a new column Literacy_Status:

“Literate” = “Yes, read and write” / “Yes, read only”

“Illiterate” = “No”


Standardized values:

Uniform region names to match shapefile (e.g., “Greater Accra”, “Northern East” → “North East”)

Trimmed extra spaces and corrected case inconsistencies.

4️⃣ Data Validation

Checked region and literacy distribution to confirm values aligned with Ghana’s expected population spread.

Verified data relationships between age, region, and literacy rate made logical sense.

Sampled random records to ensure cleaning did not distort meaning.


✅ Final Output

A clean dataset with the following columns:
| Region | Residence_Type | Sex | Age | Literacy | Literacy_Status | School_Attendance | Highest_Education | Weight |

Saved as:
cleaned_data/PHC2021_Microdata_Clean.csv