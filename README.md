# Railway Performance & Delay Command Center

## Project Title

**Railway Performance & Delay Command Center**

## Project Overview

Railway Performance & Delay Command Center is a data analytics and business intelligence project developed to monitor railway operations, passenger activity, revenue, train punctuality, delays, cancellations, stations, and routes.

The project converts operational data into an interactive Power BI command center so users can quickly identify performance problems, compare routes and stations, understand delay patterns, and support data-driven operational decisions.

The solution follows an end-to-end analytics workflow:

**Data Preparation → MySQL Database → ETL & Data Cleaning → Power BI Data Model → DAX Measures → Dashboard Development → Business Insights**

> **Industry:** Indian Railway Industry  
> **Technology Stack:** MySQL + Power BI + DAX + ETL

## Project Objectives

- Monitor overall railway operational performance.
- Track train punctuality and average delays.
- Analyze passenger volumes and revenue.
- Identify high-delay trains, routes, and stations.
- Analyze cancellation trends and cancellation percentages.
- Understand delay reasons and their operational impact.
- Compare operations and punctuality across zones.
- Provide an interactive command center for data-driven operational decisions.
- Demonstrate an end-to-end analytics workflow using SQL, ETL, Power BI, and DAX.

## Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **MySQL** | Relational database creation, table management, relationships, and SQL-based data storage |
| **Power BI Desktop** | Data modeling, interactive visualizations, dashboard development, and reporting |
| **Power Query / ETL** | Data extraction, transformation, cleaning, type correction, and loading |
| **DAX** | Calculated measures and business KPIs |
| **Microsoft Excel / CSV** | Initial dataset preparation and data exchange during ETL |

## Dataset Description

The project uses a **synthetic railway operations dataset** designed to represent realistic Indian railway operational scenarios.

The dataset includes:

- Train operations
- Train and train attributes
- Stations
- Routes
- Passengers
- Revenue
- Delay information
- Cancellation information
- Travel dates
- Operational attributes
- Delay reason categories

### Dataset Source

The dataset was created as synthetic project data based on real-world railway operational patterns. It is intended for analytics, dashboard development, and academic/project demonstration.

**Important:** It is **not an official Indian Railways operational dataset**.

The data was intentionally prepared with practical data-quality issues so the project demonstrates a complete ETL and data-cleaning workflow.

## SQL Analysis

A MySQL database named `railway_performance_db` was created to organize the railway data in a relational structure.

### Database Tables

| Table | Purpose | Main Information |
|---|---|---|
| `Trains` | Train master data | Train ID, train name, train attributes |
| `Stations` | Station master data | Station ID, station name, station details |
| `Routes` | Route information | Route ID and route/station relationships |
| `Delay_Reasons` | Delay classification | Delay reason categories |
| `Train_Operations` | Core fact/transaction table | Travel date, train, route, origin, destination, passengers, revenue, delay, and cancellation details |

The `Train_Operations` table acts as the central operational table, while `Trains`, `Stations`, `Routes`, and `Delay_Reasons` provide descriptive/master information for analysis.

SQL/database work includes:

- Database and table creation
- Primary-key and foreign-key relationships
- Relational data organization
- Operational data storage
- Preparation of structured data for Power BI
- Validation of relationships and data integrity

## Power BI Dashboard

The Power BI report is designed as **four focused dashboard pages**, with each page serving a specific business purpose.

### Page 1 – Executive Overview

The Executive Overview provides a high-level view of railway performance using:

- Total Operations KPI
- Total Passengers KPI
- Total Revenue KPI
- Average Delay KPI
- ON Time % KPI
- Cancellation % KPI
- Monthly Average Delay
- Monthly Revenue
- Operations by Delay Reason
- Operations by Zone

### Page 2 – Train Performance

Train-level performance analysis includes:

- Top 10 Trains by ON Time %
- Total Passengers by Train Name
- Total Revenue by Train Name
- Top 10 Trains by Cancellation %
- Top 10 Trains by Average Delay

### Page 3 – Station & Route Analysis

Station, route, and zone analysis includes:

- Top 10 Stations by Total Operations
- Top 10 Routes by Average Delay
- Operations by Zone
- ON Time % by Zone
- Top 10 Stations by Average Delay
- Top 10 Routes by Total Operations

### Page 4 – Delay & Cancellation Analysis

Detailed delay and cancellation analysis includes:

- Total Cancellation by Month
- Cancellation % Trend (Monthly)
- Cancellation Status Distribution
- Delay Reason Distribution
- Average Delay by Day of Week
- Average Delay by Hour

## Key KPIs

The core DAX measures used by the dashboard include:

| KPI / Measure | Dashboard Usage |
|---|---|
| **Total Operations** | Executive Overview, Operations by Zone, Operations by Delay Reason, route/station analysis |
| **Total Passengers** | Executive Overview, Total Passengers by Train Name |
| **Total Revenue** | Executive Overview, Monthly Revenue, Total Revenue by Train Name |
| **Average Delay** | Executive Overview, monthly, train, route, station, hour, and day-of-week analysis |
| **ON Time %** | Executive Overview, ON Time % by Train Name and Zone |
| **Cancellation %** | Executive Overview, train-level analysis, monthly trend, Delay & Cancellation KPI |
| **Total Cancellations** | Delay & Cancellation analysis and monthly cancellation analysis |

## Key Insights

The dashboard is designed to help users identify and investigate:

- Overall railway operational performance.
- Average delay patterns across trains, routes, stations, hours, and days.
- Trains with lower ON Time % and higher cancellation %.
- Routes and stations with higher average delays.
- Zones with different operational volumes and punctuality performance.
- Monthly revenue and operational trends.
- Major delay reason categories.
- Monthly cancellation trends and cancellation status distribution.
- High-volume stations and routes based on total operations.

> The exact numerical findings should be read directly from the Power BI dashboard because the uploaded documentation describes the dashboard structure and measures but does not provide final KPI values.

## Project Workflow

```text
Raw / Prepared Railway Data
          ↓
Excel / CSV
          ↓
MySQL Database
          ↓
Relational Tables & Relationships
          ↓
Power Query / ETL
          ↓
Data Cleaning & Validation
          ↓
Power BI Data Model
          ↓
DAX Measures & KPIs
          ↓
Interactive Power BI Dashboard
          ↓
Business Analysis & Insights
```

### ETL Steps

1. **Extract** – Import railway operational and supporting master tables.
2. **Transform** – Select required columns, correct data types, standardize text, and prepare analytical fields.
3. **Validate** – Check nulls, duplicates, invalid values, relationships, and inconsistent categories.
4. **Load** – Apply cleaned query results to the Power BI data model.

### Data Cleaning

The project includes:

- Handling duplicate records where applicable.
- Handling blank/null values in important fields.
- Correcting data types for dates, numbers, percentages, and categorical columns.
- Standardizing train, station, route, and reason names.
- Checking inconsistent delay and cancellation values.
- Validating primary-key and foreign-key relationships.
- Checking outliers and invalid operational values.

## Repository Structure

A recommended GitHub repository structure is:

```text
Railway-Performance-Delay-Command-Center/
│
├── README.md
│
├── PowerBI/
│   └── Railway_Performance_Delay_Command_Center.pbix
│
├── SQL/
│   ├── database_creation.sql
│   ├── table_creation.sql
│   └── analysis_queries.sql
│
├── Data/
│   ├── trains.csv
│   ├── stations.csv
│   ├── routes.csv
│   ├── delay_reasons.csv
│   └── train_operations.csv
│
├── Documentation/
│   └── Project_Documentation.docx
│
└── Screenshots/
    ├── executive_overview.png
    ├── train_performance.png
    ├── station_route_analysis.png
    └── delay_cancellation_analysis.png
```

> Update the filenames above to match the actual files included in your GitHub repository.

## Dashboard Screenshots

Add the Power BI dashboard screenshots to the `Screenshots/` folder and reference them in this section.

### Executive Overview


![Executive Overview](SCREENSHOT/EXECUTIVE%20OVERVIEW.png)


### Train Performance


![Train Performance](SCREENSHOT/TRAIN%20PERFORMANCE.png)


### Station & Route Analysis

![Station & Route Analysis](SCREENSHOT/STATION%20%26%20ROUTE%20ANALYSIS.png)


### Delay & Cancellation Analysis


![Delay & Cancellation Analysis](SCREENSHOT/DELAY%20%26%20CANCELLATION%20ANALYSIS.png)


## Filters & Slicers

The dashboard supports interactive filtering using:

- Zone
- Destination Station
- Origin Station
- Train Type
- Train Name
- Travel Date

These filters allow users to drill into specific operational segments and investigate railway performance from different perspectives.

## How to Run the Project

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd Railway-Performance-Delay-Command-Center
```

### 2. Set Up MySQL

Create the database:

```sql
CREATE DATABASE railway_performance_db;
```

Create and populate the required tables using the SQL scripts in the `SQL/` folder.

### 3. Load the Dataset

Place the project CSV/Excel files in the appropriate `Data/` directory and load them into MySQL according to the database schema.

### 4. Open Power BI

Open:

```text
PowerBI/Railway_Performance_Delay_Command_Center.pbix
```

### 5. Configure the MySQL Connection

In Power BI Desktop:

**Home → Transform data / Data source settings**

Select the MySQL database connection and provide the required server, database, username, and password details.

### 6. Refresh the Data

Refresh the Power BI model after the database connection is configured.

### 7. Explore the Dashboard

Navigate through the four report pages:

1. Executive Overview
2. Train Performance
3. Station & Route Analysis
4. Delay & Cancellation Analysis

Use the slicers and visuals to investigate railway operations, delays, punctuality, revenue, passengers, routes, stations, and cancellations.

## Author

**Thanga Raj.V**(AF05265179)

Data Analytics with AI (Anudip Foundation/Pallavaram)

**Project:** Railway Performance & Delay Command Center

**Domain:** Data Analytics / Business Intelligence

**Technology:** MySQL | Power BI | DAX | Power Query / ETL
