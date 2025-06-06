# 📘 README – Food Inspections Data Analysis

## 👨‍💻 As a Data Engineer: First Steps

When receiving this dataset, a data engineer typically performs the following:

1. **Schema Validation**
   - Verify column names, data types, nullability, and primary identifiers.
   - Confirm expected formats (e.g., dates, ZIP codes, coordinates).

2. **Data Cleansing**
   - Handle missing or inconsistent values.
   - Convert data types: parse date strings, clean text columns, cast numerics.
   - Normalize values (e.g., upper/lower casing for consistency).

3. **Exploratory Data Analysis (EDA)**
   - Generate summary statistics and value counts.
   - Identify outliers, anomalies, and null distributions.
   - Check value distributions across time, category, and location.

4. **Transformation & Enrichment**
   - Extract year/month from inspection dates.
   - Split multi-violation strings into structured records.
   - Generate flags or indicators (e.g., follow-up inspection, pass/fail binary).

5. **Create Analysis-Ready Dataset**
   - Drop irrelevant or duplicate columns.
   - Format and standardize columns (e.g., Zip as string, unified date format).
   - Save to clean format (e.g., Parquet/CSV).

6. **Document Assumptions & Decisions**
   - Note fields dropped or transformed.
   - Record assumptions about violation parsing, missing values, or inspection types.

---

## 🗂 Dataset Overview

This dataset contains historical **food inspection results** from facilities across **Chicago**, including restaurants, schools, and healthcare centers.

| Column Name        | Description                                             |
|--------------------|---------------------------------------------------------|
| `Inspection ID`     | Unique identifier for each inspection                   |
| `DBA Name`          | Business name                                            |
| `AKA Name`          | Alternate business name                                  |
| `License #`         | Unique license ID for a facility                        |
| `Facility Type`     | Type of facility (e.g., Restaurant, Grocery Store)      |
| `Risk`              | Health risk level: Low, Medium, High                    |
| `Address`, `City`, `State`, `Zip` | Physical address                          |
| `Inspection Date`   | Date of the inspection                                   |
| `Inspection Type`   | Type of inspection (e.g., Canvass, Complaint)           |
| `Results`           | Outcome of inspection (e.g., Pass, Fail)                |
| `Violations`        | Text descriptions of violations                         |
| `Latitude`, `Longitude` | Geographical coordinates                          |
| `Location`          | Tuple of (Latitude, Longitude)                          |

---

## 🔄 Data Transformations (Recommended)

| Step | Transformation |
|------|----------------|
| ✅ | Convert `Inspection Date` to datetime format |
| ✅ | Parse and count violations from `Violations` text |
| ✅ | Derive year, month, weekday from `Inspection Date` |
| ✅ | Create a “Failure Flag” column from `Results` |
| ✅ | Normalize facility names to lowercase/trim |
| ✅ | Remove or handle null coordinates for mapping |

---

## ❓ Suggested Analytical Questions (20 Total)

1. How many inspections were conducted each year?
2. Which facilities have the highest number of failed inspections?
3. What is the pass/fail rate per facility type?
4. How has the number of violations changed over the years?
5. Which ZIP codes have the most failed inspections?
6. Do high-risk facilities fail more often than others?
7. What are the top 10 most frequent violations?
8. How many inspections are follow-up vs first-time?
9. Which days of the week are inspections most common?
10. Which facility types tend to have more violations?
11. Where are failed inspections located geographically?
12. Do large chains perform better than single-site businesses?
13. What’s the average number of violations per inspection?
14. Which neighborhoods have the most repeat offenders?
15. Do more inspections fail in specific months?
16. Are there failed inspections without recorded violations?
17. Are certain inspectors more likely to fail a facility? *(if data exists)*
18. Which facilities fail repeatedly across years?
19. What’s the failure rate for restaurants vs other facility types?
20. How often do “License Re-Inspections” happen, and do they pass?

---

## 📊 Expected Output Formats

| Output Type    | Example Insight                                  |
|----------------|--------------------------------------------------|
| Bar Chart      | Pass vs Fail counts per year                     |
| Pie Chart      | Distribution of Risk Levels                      |
| Line Chart     | Trend of inspections over time                   |
| Table          | Top 10 facilities by number of violations        |
| Heatmap        | ZIP codes with highest fails                     |
| Map            | Locations of failed inspections                  |
| Histogram      | Violations per inspection                        |
| Word Cloud     | Most frequent words in violation descriptions    |

---



## 🧠 End Goal

Enable your teammate to:
- Practice real-world SQL
- Generate health and compliance insights
- Deliver clean, interpretable visuals
