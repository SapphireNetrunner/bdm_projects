# BigData 2025 Template Repository

![TartuLogo](./images/logo_ut_0.png)

Project [Big Data](https://courses.cs.ut.ee/2025/bdm/spring/Main/HomePage) is provided by [University of Tartu](https://courses.cs.ut.ee/).

*Students:* [Rohan Iyer, Karl Gustav Loog, Vladislav Samsonov, Mark Erik Aan]

## Queries

## Requirements

## Note for Students
- Clone the created repository offline.
- Add your name and surname into the Readme file and your teammates as collaborators.
- Complete the field above.
- Make any changes to your repository according to the specific assignment.
- Ensure code reproducibility and instructions on how to replicate the results.
- Add an open-source license, e.g., Apache 2.0.
- Convert README to PDF.
- Keep one report for all projects.

## NYC Taxi Data Analysis

This notebook includes data preparation, running the queries, and saving the results using PySpark. Below is a summary of the key steps and operations performed:

1. *Setup and Initialization*:
   - Import necessary libraries and modules.
   - Create a Spark session for the analysis.

2. *Data Loading and Cleaning*:
   - Load the taxi trip data from a CSV file.
   - Drop rows with missing latitude and longitude values.

3. *Geospatial Processing*:
   - Load NYC borough boundaries from a GeoJSON file.
   - Convert borough boundaries to Shapely polygons.
   - Define a UDF to determine the borough for given coordinates.
   - Enrich the taxi dataset with borough information for pickup and dropoff locations.

4. *Timestamp Conversion and Trip Duration Calculation*:
   - Convert pickup and dropoff times to Unix timestamps.
   - Calculate trip duration.
   - Filter out trips with negative duration or longer than 4 hours.

5. *Idle Time Calculation*:
   - Compute idle time for each taxi using window functions.

6. *Aggregations*:
   - Calculate utilization per taxi.
   - Compute average time to find the next fare per borough.
   - Count trips within the same borough and between different boroughs.

7. *Final Data Preparation*:
   - Join various aggregated dataframes to create a final dataframe.
   - Save the final dataframe as a Parquet file.

8. *Additional Aggregations and Saving Results*:
   - Load Parquet files and perform additional aggregations.
   - Save results as CSV files.