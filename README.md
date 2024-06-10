# PLAN MY DAY

Welcome to the PLAN MY DAY app! This application is designed for the Databricks DATA + AI Summit 2024. It helps users plan their day by leveraging data from open street maps and advanced AI models.

## Table of Contents
- [Overview](#overview)
- [Installation](#installation)
- [Data Processing](#data-processing)
- [App Functionality](#app-functionality)
- [Usage](#usage)
- [Conclusion](#conclusion)

## Overview

The PLAN MY DAY app combines data processing and AI-driven insights to provide personalized recommendations for tourist attractions in North America. The app reads and processes data from open street maps and utilizes machine learning models to offer suggestions based on user preferences.

## Installation

To run the PLAN MY DAY app, you need to install the required libraries and access to Databricks. You can install them using the following command on your databricks python notebook:

```bash
%pip install langchain langchain_community mlflow databricks-sql databricks-vectorsearch
```

After installing the necessary libraries, restart the Python environment to ensure all changes take effect.

## Data Processing

The data processing steps are handled in the `data_preprocessor.ipynb` notebook. This notebook reads data from the Databricks table `open_street_map_tourist_attractions_for_north_america`, displays the data, and filters out rows with null values in the `name` column. Here's a brief overview of the steps:

1. Read data from the Databricks table:
    ```python
    df = spark.read.table("dbaisummit.default.open_street_map_tourist_attractions_for_north_america")
    df.show()
    ```

2. Filter out rows with null values in the `name` column:
    ```python
    df = df.filter(df.name.isNotNull())
    ```

## App Functionality

The main functionality of the app is encapsulated in the `plan_my_day.ipynb` notebook. This notebook sets up the environment, installs necessary libraries, and imports modules for language models and vector search functionality.

### Key Components:

- **LangChain Integration**: Utilizes the `langchain` library to leverage language models for generating recommendations.
- **MLflow**: Integrates with MLflow for managing machine learning experiments and models.
- **Databricks Vector Search**: Employs Databricks Vector Search for efficient retrieval of relevant tourist attractions.

## Usage

To use the PLAN MY DAY app, follow these steps:

1. Ensure all required libraries are installed.
2. Run the data processing steps in `data_preprocessor.ipynb` to prepare the dataset.
3. Execute the `plan_my_day.ipynb` notebook to initialize the app and start generating recommendations.

## Conclusion

The PLAN MY DAY app is designed to enhance your travel experience by providing personalized recommendations for tourist attractions. By leveraging advanced AI models and data processing techniques, the app ensures that you get the most out of your day. We hope you find this tool useful and look forward to your feedback and contributions. Thank you for using PLAN MY DAY!
