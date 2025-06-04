# Cyclistic Case Study: Data Processing and Cleaning

This README outlines the data processing and cleaning steps performed for the Cyclistic Case Study as part of the Google Professional Data Analytics Certificate. The goal of this analysis is to uncover insights into how annual members and casual riders use Cyclistic’s bike-sharing service differently and to inform strategies for converting casual riders into annual members.

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Data Cleaning](#data-cleaning)
- [Data Transformation](#data-transformation)
- [Data Preparation](#data-preparation)
- [Next Steps](#next-steps)

## Project Overview

This project focuses on the **Prepare** and **Process** phase of the [data analysis process](https://www.linkedin.com/pulse/six-data-analysis-phases-gert-l%C3%B5hmus/), ensuring that the raw data is clean, consistent, and ready for analysis. The process includes:

1. **Understanding the Data Sources**: Reviewing formats and structures.
2. **Data Cleaning**: Addressing quality issues and inconsistencies.
3. **Data Transformation**: Reformatting and reshaping data for analysis.
4. **Data Preparation**: Structuring the cleaned data for deeper analysis.

## Data Sources

The data for this analysis comes from Cyclistic’s bike-share database. It includes details such as ride durations, start and end times, user types (annual member or casual rider), and other relevant attributes. The datasets are publicly available [here](https://divvy-tripdata.s3.amazonaws.com/index.html).

## Data Cleaning

Data cleaning ensures the accuracy and reliability of the analysis. Key steps include:

- **Handling Missing Values**: Identifying and imputing or removing missing records.
- **Removing Duplicates**: Ensuring no duplicate rides skew the analysis.
- **Standardizing Formats**: Unifying date-time formats and other data types.
- **Correcting Anomalies**: Addressing any outliers or unexpected data patterns.

## Data Transformation

This phase reshapes the data to make it analysis-ready. Tasks include:

- **Feature Engineering**: Creating new variables (e.g., ride duration in minutes).
- **Data Aggregation**: Summarizing data for exploratory analysis.
- **Derived Metrics**: Calculating insights such as average trip duration.
- **Data Type Conversion**: Ensuring consistency across columns.

## Data Preparation

The final preparation step structures the cleaned and transformed data for in-depth analysis:

- **Segmenting Data**: Splitting rides by user type (annual members vs. casual riders).
- **Subsetting Data**: Filtering data as needed for specific questions.
- **Exporting Datasets**: Preparing files for visualization and statistical analysis.

Documenting each step is crucial for ensuring reproducibility and transparency.

## Next Steps

For insights, visualizations, and recommendations based on this prepared data, please refer to the [full case study presentation](https://docs.google.com/presentation/d/1XoTD_Y4Lz1M9pKxxiJEaePUnxANE6NitWvnH_N07Sds/edit?usp=sharing).
