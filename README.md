# SQL Chicago Data Analysis Project – IBM Data Engineering Professional Certificate

## Overview

This project explores and analyzes real-world datasets from the City of Chicago using SQL within a Jupyter Notebook.
It was completed as the final project for **Course 5 – Databases and SQL for Data Science with Python**
in the [IBM Data Engineering Professional Certificate](https://www.coursera.org/professional-certificates/ibm-data-engineer).

The analysis is performed using SQLite and `%sql` magic commands, combining Python and SQL to uncover insights about crime rates, public schools, and socioeconomic conditions in Chicago.

---

## Objectives

- Create and connect to a SQLite database using Jupyter and SQL magic
- Import CSV datasets into pandas and persist them as relational tables in SQLite
- Perform SQL queries to extract insights using filtering, grouping, and aggregation
- Apply subqueries and joins to analyze relationships across datasets
- Investigate correlations between crime rates, community demographics, and school safety

---

## Tools & Technologies

| Category          | Tools/Technologies             |
|-------------------|--------------------------------|
| **Languages**     | Python, SQL                    |
| **Libraries**     | pandas, sqlite3, ipython-sql   |
| **Database**      | SQLite                         |
| **Environment**   | Jupyter Notebook               |
| **File Formats**  | CSV                            |

---

## Datasets Used

1. **Chicago Census Data**  
   Socioeconomic indicators by community area (2008–2012)  
   [Source](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)

2. **Chicago Public Schools Progress Report Cards**  
   Performance and safety data (2011–2012)  
   [Source](https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t)

3. **Chicago Crime Data**  
   Reported crimes from 2001 to present  
   [Source](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2)

> **Note:** Cleaned and reduced versions of the datasets were provided by IBM for educational use.

---

## Tasks Completed

- Created a new SQLite database and established a connection using `%load_ext sql`
- Loaded three CSV files into pandas DataFrames
- Created corresponding tables in SQLite using pandas `.to_sql()` method
- Queried data using SQL operations:
  - Filtering with `WHERE` and `LIKE` clauses
  - Joining and grouping data across tables
  - Using aggregation functions (`COUNT`, `AVG`)
  - Writing subqueries to solve analytical problems
- Answered 10 domain-specific questions involving:
  - Crimes involving minors and children
  - School safety scores grouped by type
  - Community areas with high poverty and hardship
  - Identifying the most crime-prone neighborhood

---

## Sample SQL Queries

```sql
-- Total number of crimes
SELECT COUNT(*) FROM CHICAGO_CRIME_DATA;

-- Community areas with per capita income < $11,000
SELECT COMMUNITY_AREA_NAME, COMMUNITY_AREA_NUMBER
FROM CENSUS_DATA
WHERE PER_CAPITA_INCOME < 11000;

-- Crimes committed at school locations (distinct types)
SELECT DISTINCT PRIMARY_TYPE
FROM CHICAGO_CRIME_DATA
WHERE LOCATION_DESCRIPTION LIKE '%SCHOOL%';
```

---

## Key Insights

- **Riverdale** had both the highest hardship index and highest percentage of households below the poverty line.
- **Austin (Community Area 25)** was the most crime-prone area in the dataset.
- Safety scores varied across school types, with high schools and elementary schools showing similar average ratings.

---

## Repository Structure

```plaintext
SQL_Chicago_Data_Analysis_Project/
├── README.md                                    # Project overview and instructions
├── data/
│   ├── ChicagoCensusData.csv                    # Socioeconomic data by community area
│   ├── ChicagoCrimeData.csv                     # Crime records
│   └── ChicagoPublicSchools.csv                 # School performance and safety scores
├── images/                                      # Screenshots of database setup and SQL query results
│   ├── low_income_areas.png                     # Community areas with low per capita income (Problem 2)
│   ├── most_crime_prone_area.png                # Area with the highest crime count using a subquery (Problem 10)
│   ├── school_crimes_summary.png                # Types of crimes reported at school locations (Problem 5)
│   ├── table_creation_and_database_setup.png    # Creating SQLite DB and loading tables using pandas and df.to_sql()
│   └── total_crimes_count.png                   # Total number of crimes in the dataset (Problem 1)
├── notebook/
│   └── SQL_Chicago_Data_Analysis_Project.ipynb  # Final notebook with all tasks and query outputs
```

---

## License

This project was completed as part of the IBM Data Engineering Professional Certificate and is intended for educational use.

## Links

- Course Page - [Databases and SQL for Data Science with Python](https://www.coursera.org/learn/sql-data-science)
- [GitHub Profile](https://github.com/royungar)
- [GitHub Repository](https://github.com/royungar/SQL_Chicago_Data_Analysis_Project)