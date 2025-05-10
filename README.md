[![DOI](https://zenodo.org/badge/922587650.svg)](https://doi.org/10.5281/zenodo.15379987)
# Mitochondrial Morphology Analysis Script

This Jupyter Notebook-based Python script performs a comprehensive analysis of mitochondrial morphology data. It includes data loading, descriptive statistics, correlation analysis, dimensionality reduction (PCA), clustering (K-Means), and statistical testing.

## Key Improvements

This version of the script includes several key enhancements:

*   **Deprecated Library Updates:** Addressed deprecation warnings and updated function calls from older versions of libraries (e.g. `sklearn`, `scipy`, and `kneed`).
*   **Improved K-Means Initialization:** Added `n_init` and `random_state` parameters to the `KMeans` initialization, increasing reproducibility and preventing depreciation warnings.
*    **Corrected Correlation Calculations:** Added `.dropna()` to the pandas series before running to increase accuracy of the correlation coefficient calculations.
*   **Bonferroni Correction Calculation:** Improved calculation of Bonferroni correction.
*   **Clearer Code:** Enhanced code readability with better comments and formatting.
*   **Output Clarity:** Added print statements and title headers for better understanding of tables and plots generated. Added `display` to specific outputs to improve table formatting.
*   **Robust Statistical Analysis:** Ensured that the statistical functions were correctly called from `scipy.stats`, and added Dunn's post-hoc test for pairwise comparisons and a heatmap to visualize those results.
*  **Saved all PNG files:** Readded all of the saved PNG files.
*  **Corrected Heatmaps:** The heatmaps now have a title, x and y labels. Additionally, Dunn's Post-hoc test heatmap will be saved in the correct place.
  
## Key Functionalities

This script performs the following analyses on mitochondrial morphology data:

1.  **Data Loading and Inspection:**
    *   Loads data from an Excel or CSV file into a Pandas DataFrame.
    *   Displays the first few rows of the DataFrame for inspection.
    *   Calculates and displays the number of unique image names per cell type.
    *   Generates and displays descriptive statistics for all numerical columns.

2.  **Box Plots Visualization:**
    *   Creates box plots for each numerical parameter, showing the overall distribution and distributions for different cell types.

3.  **Correlation Analysis:**
    *   Computes Spearman or Pearson correlation coefficients between all numeric parameters, handling missing data
    *   Applies Bonferroni correction to the correlation p-values for multiple hypothesis testing.
    *   Marks significant correlations (p-value < 0.05) with `**` in the correlation table.
    *   Generates a heatmap visualization of the correlation matrix.

4.  **Principal Component Analysis (PCA):**
    *   PCA is applied to reduce the dimensionality of the numerical data into two components.
    *   Generates a scatter plot of the reduced data.

5.  **K-Means Clustering:**
    *   Uses the Elbow method (KneeLocator) to determine the optimal number of clusters.
    *   Performs K-Means clustering on the PCA-reduced data.
    *   Calculates the Silhouette Score to evaluate the quality of the clustering.
    *   Displays descriptive statistics of each cluster.
    *   Visualizes the clusters using a scatter plot overlaid on the PCA data.

6.  **Cluster Analysis:**
    *   Creates box plots visualizing the parameter differences within the clusters.
    *   Generates a heatmap showing the mean parameter values for each cluster.
    *   Calculates and displays the percentage of cells from each cell type within each cluster.
    *   Calculates and displays the total number of cells from each cell type within each cluster.
   *    Visualizes the cell counts per cluster and cell type using a stacked bar plot.
   *   Visualizes the cell counts per cluster and exposure condition using a stacked bar plot.

7.  **Statistical Testing:**
    *   Performs Shapiro-Wilk tests to assess the normality of each parameter across all data.
    *   Levene's test is performed to assess the equality of variances between different exposure groups.
    *   Performs Kruskal-Wallis H-tests to assess statistical differences in each parameter across different exposure groups.
    *   Conducts Dunn's post-hoc test with Bonferroni correction for each parameter to determine the pairwise differences between exposure groups
    *    Generates a heatmap of all p-values of Dunn's Post-hoc test with Bonferroni correction


## Getting Started

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/farhanaugustine/3D_Mitochondrial_Analysis_Script.git
    cd 3D_Mitochondrial_Analysis_Script # or `cd path/to/the/cloned/repo`
    ```

2.  **Install Requirements:**
    ```bash
     conda env create -f environment.yaml
    ```
    **install jupyter notebook using pip**
    ```bash
    pip install notebook 
    ```

3.  **Run the Script:**
    *   Open the Jupyter Notebook (`.ipynb`) file in your Jupyter environment.
    *   Update the `file_path` variable with the correct path to your data file.
    *   Execute the code cells according to your own needs.
    *   Ensure that you read the comments to help you understand what you should and should not change about the script.

4.  **Analyze Output:**
    *   Check the outputs in your notebook to see how the code is being run.

## Contributing

Please feel free to contribute by raising issues or submitting pull requests to the repository.
