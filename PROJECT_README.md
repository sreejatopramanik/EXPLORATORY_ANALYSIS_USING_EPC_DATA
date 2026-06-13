
# README: Exploratory Data Analysis with EPC Industry Data and MNIST Clustering

## Project Overview
This notebook performs an Exploratory Data Analysis (EDA) on an EPC (Engineering, Procurement, and Construction) Industry dataset, focusing on data loading, cleaning, statistical summarization, correlation analysis, outlier detection, and feature engineering. Additionally, it demonstrates K-Means clustering on the MNIST digits dataset, including F1 score evaluation.

## Dataset
*   **EPC Industry Analytics Demo Data**: An Excel file (`EPC_Industry_Analytics_Demo.xlsx`) containing various operational metrics for an EPC industry project. This dataset is loaded and analyzed for insights.
*   **MNIST Digits Dataset**: A classic dataset of handwritten digits (0-9), used for demonstrating K-Means clustering and evaluating its performance.

## Notebook Structure and Key Steps

### 1. Data Loading and Initial Exploration
*   Installation of `gdown` for downloading the EPC dataset from Google Drive.
*   Loading `EPC_Industry_Analytics_Demo.xlsx` into a pandas DataFrame.
*   Displaying the shape, data types, and initial missing value counts.

### 2. Data Cleaning
*   Identifying and counting duplicate rows.
*   Replacing various representations of missing values (blank spaces, empty strings, 'None', '-') with `np.nan`.
*   Filling missing values in numeric columns with their respective medians.

### 3. Exploratory Data Analysis (EDA)
*   Generating a comprehensive statistical summary of the DataFrame using `.describe(include='all')`.
*   Calculating and printing the correlation matrix for all numeric columns.

### 4. Outlier Detection
*   Implementing a loop to calculate the Interquartile Range (IQR) for each numeric column.
*   Counting outliers (values outside Q1 - 1.5*IQR and Q3 + 1.5*IQR) and storing them in a dictionary.

### 5. Group-Based Aggregation
*   Grouping the EPC data by the first categorical column.
*   Calculating the mean, median, and sum for all numeric columns within each group.

### 6. Feature Engineering
*   Creating a new feature `New_Feature` by dividing the first numeric column by (the second numeric column + 1).

### 7. Ranking Analysis
*   Creating a `Rank` column based on the first numeric column in descending order.

### 8. Conditional Filtering
*   Filtering the DataFrame to include rows where the first numeric column's value is strictly greater than its mean.

### 9. MNIST Data Loading
*   Loading the MNIST digits dataset using `sklearn.datasets.load_digits`.
*   Separating features (`X`) and target labels (`y`) and printing their shapes.

### 10. K-Means Clustering
*   Applying K-Means clustering to the MNIST features (`X`) with `n_clusters=10`.
*   Assigning cluster labels to `kmeans_labels`.

### 11. F1 Score Evaluation for Clustering
*   Mapping K-Means cluster labels to the true MNIST digit labels by finding the most frequent true label within each cluster.
*   Calculating and printing the macro-averaged F1 score using `sklearn.metrics.f1_score`.

## Technologies Used
*   `pandas` for data manipulation and analysis.
*   `numpy` for numerical operations.
*   `gdown` for downloading files from Google Drive.
*   `sklearn` for dataset loading, clustering (K-Means), and evaluation metrics (f1_score).
*   `scipy.stats` for statistical operations (mode).
