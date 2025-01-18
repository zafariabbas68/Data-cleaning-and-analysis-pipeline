# Data-cleaning-and-analysis-pipeline
In this project, we aimed at constructing a robust data cleaning analysis pipeline tailored to preprocess, analyze, and evaluate the complex CRIMES dataset for deriving further insights.
# Data Cleaning and Analysis Pipeline for the CRIMES Dataset

## Project Overview

This project focuses on constructing a robust data cleaning and analysis pipeline for the CRIMES dataset, which contains historical crime records from the city of Boston, MA. The dataset includes various features such as the nature of crimes, their locations, and times, offering significant opportunities for data-driven insights. The project addresses challenges like missing data, inconsistencies, and large size through a systematic data preparation process.

## Objectives

1. **Data Preprocessing Pipeline**: Design and implement a pipeline to handle missing values, outliers, and normalization issues, ensuring data readiness for analysis and machine learning.
2. **Actionable Insights**: Use the cleaned dataset for multi-class linear classification, demonstrating the value of the cleaning pipeline in refining knowledge.
3. **Flexibility and Replicability**: Ensure the pipeline can be easily understood, reused, and adapted to similar datasets.

## Data Exploration

The initial exploration revealed that the dataset, although mostly clean, required specific treatments:
- Manual typing errors in the `STREET` column.
- Redundancy in geospatial attributes.
- Missing values in key columns like `DISTRICT`, `REPORTING_AREA`, and `UCR_PART`.

## Pipeline Implementation

### 1. Data Cleaning
- **Null Values and Outliers**: Approximated missing geospatial data using the `STREET` column and employed MICE for other columns.
- **Consistency**: Standardized values and corrected typos in street names.
- **Redundancy**: Removed redundant columns like `OCCURRED_ON_DATE` and `Location`.
- **Record Linkage**: Ensured integrity across key columns.

### 2. Preparation for Classification
- **Rare Values Removal**: Filtered out values appearing in less than 5% of cases.
- **Anomaly Detection**: Used Isolation Forest for detecting extreme geospatial values.
- **Scaling and Encoding**: Applied label encoding and one-hot encoding as needed.
- **Feature Selection**: Leveraged Random Forest to identify and drop less important features.

## Results

Using a basic feed-forward neural network for multi-class classification, the cleaned dataset significantly outperformed the messy dataset:
- **Test Accuracy**: 0.91 (cleaned) vs. 0.84 (messy)
- **Precision, Recall, and F1 Score**: All metrics improved with the cleaned dataset.

## Challenges and Future Directions

- **Resource Limitations**: The dataset's size constrained some techniques, which could be improved with better infrastructure.
- **Geospatial Data Handling**: More advanced geospatial techniques could be explored with reliable APIs and industry-grade geolocators.

## Conclusion

The project successfully demonstrated the importance of data cleaning in enhancing the efficiency of analysis, providing a replicable and adaptable pipeline for complex datasets.

## Authors

- Roman Jules Tiédrez
- Hadi
- Ghulam Abbas Zafari

## License

This project is licensed under the MIT License. See the LICENSE file for details.

