# Python Project for Data Engineering

This repository contains code for a data engineering project that focuses on the ETL (Extract, Transform, Load) process using Python and various libraries. The project aims to extract data from JSON files, transform the data by applying currency conversion and formatting, and then load the transformed data into a CSV file.

## Objectives

In this project, we will achieve the following objectives:

1. Run the ETL process.
2. Extract bank and market cap data from the JSON files `bank_market_cap_1.json` and `bank_market_cap_2.json`.
3. Transform the market cap currency using the exchange rate data from the `exchange_rates.csv` file.
4. Load the transformed data into a separate CSV file named `bank_market_cap_gbp.csv`.

## Getting Started

To get started with this project, follow the steps outlined below.

### Installation

Before you begin, make sure you have the required libraries installed. You can install them using the following commands:

```bash
pip install pandas==1.3.3
pip install requests==2.26.0
```

### Data Extraction

The extraction process involves reading JSON files and loading them into Pandas DataFrames.

#### JSON Extract Function

The `extract_from_json` function extracts data from a JSON file and returns a DataFrame.

### Extract Function

The `extract` function locates JSON files (`bank_market_cap_1.json` and `bank_market_cap_2.json`) and uses the `extract_from_json` function to extract data. The extracted data is stored in a Pandas DataFrame with columns `Name` and `Market Cap (US$ Billion)`.

### Exchange Rate Extraction

Exchange rates are extracted from the `exchange_rates.csv` file to find the exchange rate for British pounds (GBP).

## Data Transformation

The transformation process involves converting the market cap currency to GBP, rounding the values to three decimal places, and renaming the column.

### Transform Function

The `transform` function applies the following transformations:

1. Converts the `Market Cap (US$ Billion)` column from USD to GBP using the exchange rate.
2. Rounds the `Market Cap (GBP$ Billion)` column to three decimal places.
3. Renames the `Market Cap (US$ Billion)` column to `Market Cap (GBP$ Billion)`.

## Data Loading

The loading process involves saving the transformed data into a CSV file.

### Load Function

The `load` function takes a DataFrame and saves it to a CSV file named `bank_market_cap_gbp.csv` with the index set to `False`.

## Logging

A logging function `log` is provided to log the different phases of the ETL process.

## Running the ETL Process

To execute the ETL process, follow these steps:

1. Start the extraction phase by calling the `extract` function. Log the process as "Extract phase Started".
2. Start the transform phase by calling the `transform` function. Log the process as "Transform phase Started".
3. Start the load phase by calling the `load` function. Log the process as "Load phase Started".

## Authors

- Ramesh Sannareddy
- Joseph Santrcangelo
- Azim Hirjani

### Other Contributors

- Aamir Ali

## License

This project is licensed under the terms of the [MIT License](https://cognitiveclass.ai/mit-license?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0221ENSkillsNetwork899-2023-01-01&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBM-DA0321EN-SkillsNetwork-21426264&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ).
