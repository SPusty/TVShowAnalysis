# TV Shows Analysis Dashboard | Power BI

## Objective

This project explores TV shows data from the [TVmaze API](https://www.tvmaze.com/api) using Microsoft PowerBI.

The goal is to analyse TV shows based on the premiere year, genres, ratings, languages, and current status through an interactive dashboard.

The dashboard helps users explore TV show trends and compare different categories of shows.

## Tools & Technologies

-   **Postman** -- Validated TVmaze API response
-   **Microsoft Power BI Desktop** -- Developed report and published dashboard to MyWorkspace
-   **Power Query** -- Extracted, cleaned, and transformed the data
-   **DAX** -- Measures and calculated columns

## Data Source

The project uses the TVmaze public API: `https://api.tvmaze.com/shows?page=0`

The API provides information about TV shows, including:

-   Show name and ID
-   Premiere date
-   Genres
-   Average rating
-   Network
-   Language
-   Show status
-   Schedule Day, Time
-   Official website

**Note:** The current API request retrieves one page of results. It does not represent the complete TVmaze catalogue.

## Data Preparation -- Power Query

The API returns JSON data containing nested records and lists. 
Power Query was used to transform this data into a table suitable for analysis.

Main transformation steps:

1.  Connected Power BI to the TVmaze API
2.  Expanded nested JSON records and lists
3.  Extracted relevant show details
4.  Expanded genre information for genre-based analysis
5.  Combined schedule days into a single column
6.  Handled missing and null values
7.  Prepared columns for reporting and analysis

**Note:** A show can appear in multiple rows because it may belong to multiple genres. The unique TVmaze show ID is used to avoid counting the same show multiple times in overall show counts.

## Data Model

1.   `show_details` -- Contains TV show information.
2.  `Date` -- A dedicated calendar table for time-based analysis. The Date table is connected to the show's premiere date.

## DAX Measures

1. Total TV Shows, counts unique TV shows using their IDs
2. YoY Growth, by comparing the current and previous year
3. Highest-rated show, from the list of Running Shows
4. Top-rated genres based on highest average rating

## Dashboard Features

### 1. KPI Cards

-   Total TV Shows
-   Year-over-Year Growth
-   Highest-Rated Running Show
-   Top 3 Highest-Rated Genres

### 2. Interactive Slicers

-   Show Status
-   Language
-   Genre

### 3. Show Count by Rating

Displays the distribution of TV shows across rating categories.

### 4. Top 5 Genres

Compares the five genres with the highest number of distinct TV shows.

### 5. Yearly Show Trend

A line chart showing how the number of TV show premieres changes over the years.

### 6. Show Details Table

Provides detailed information about individual TV shows.

## Key Learning Outcomes

-   Connecting Power BI to a REST API
-   Working with JSON data
-   Cleaning and transforming data using Power Query by handling nested records and lists
-   Building a date table and establish relationships between tables
-   Writing DAX measures and calculated columns
-   Creating interactive reports using slicers and visualisations

