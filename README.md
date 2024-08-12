# Lambda Function for Pharmacy Territory Assignment

This Python script is a Lambda function designed to assign pharmacies to salespersons' territories based on geographical data and distances.

## Overview

The script processes pharmacy data, salesperson distance data, and neighboring district information to create an initial assignment of pharmacies to salespersons. It then generates a pharmacy matrix for further processing.

## Key Features

1. **Data Processing**: 
   - Reads pharmacy data, salesperson distance data, and neighboring district information from S3 buckets.
   - Uses pandas for data manipulation.

2. **Territory Assignment**:
   - Assigns home territories to salespersons based on postal codes.
   - Handles cases where a salesperson has no pharmacies in their home territory by assigning the nearest neighboring territory.

3. **Distance Calculation**:
   - Finds the nearest clinic for each salesperson's territory.
   - Utilizes distance data to optimize assignments.

4. **Pharmacy Matrix Creation**:
   - Generates a summary matrix of pharmacies grouped by district.
   - Assigns salespersons to each district in the matrix.

5. **Output Generation**:
   - Stores the pharmacy matrix and initial territory assignments in S3.
   - Creates and updates an algorithm metadata file for tracking the assignment process.

## Key Points to Notice

1. **Environment Variables**: Uses environment variables for configuration (e.g., `BUCKET_NAME`).

2. **Error Handling**: Implements try-except blocks for S3 operations.

3. **Logging**: Utilizes a custom logging utility for tracking the process.

4. **Nested Functions**: Defines several nested functions for specific tasks (e.g., `find_nearest_clinic`, `nearest_neighbour`).

5. **Data Structures**: Uses dictionaries and pandas DataFrames for efficient data manipulation.

6. **Recursion**: The `find_neighbour_territory` function uses a recursive approach to find unoccupied neighboring territories.

7. **Flexible Configuration**: Allows for dynamic configuration of salespersons and their territories.

## Output

The function produces several outputs stored in S3:

1. A pharmacy matrix CSV file.
2. An initial territory assignment JSON file.
3. An updated algorithm metadata JSON file.
4. Log files for debugging and monitoring.

## Next Steps

The `isComplete` flag in the algorithm metadata suggests that this is part of a larger process, possibly involving step functions for further optimization or processing.
