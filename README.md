# Crypto Clustering Challenge

## Project Overview
The goal of this project is to use unsupervised learning to identify the impactful clusters of cryptocurrencies. By using techniques that use the K-means algorithm and Principal Component Analysis (PCA), we can classify cryptocurrencies based on their price fluctuations during specific timeframes. A successful program would give us valuable insights on the current standing of cryptocurrencies and its ongoing market behaviors.

## Installation Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ezwang8/CryptoClustering.git
   ```

2. **Make sure Python is installed:**
   Verify Python's installation with:
   ```bash
   python --version
   ```
   If Python is not installed, download it from [python.org](https://www.python.org/downloads/).

3. **Install Jupyter Notebook:**
   If Jupyter is not installed, run:
   ```bash
   pip install jupyter
   ```

4. **Install Necessary Packages:**

   - Install `pandas` for data manipulation and analysis:
     ```bash
     pip install pandas
     ```

   - Install `scikit-learn` for K-Means clustering and PCA:
     ```bash
     pip install scikit-learn
     ```

   - Install `matplotlib` for data visualization:
     ```bash
     pip install matplotlib
     ```

   - Install `hvplot` for interactive plotting:
     ```bash
     pip install hvplot
     ```

5. **Navigate to the Project Directory:**
   ```bash
   cd CryptoClustering
   ```

6. **Launch Jupyter Notebook:**
   Open the notebook interface:
   ```bash
   jupyter notebook
   ```

7. **Open the Notebook:**
   In Jupyter, locate the `Crypto_Clustering.ipynb` file and run the cells for analysis.

## File Roles
- **Crypto_Clustering.ipynb:** The main script that performs the analysis. It retrieves, processes, and analyzes the data from the "crypto_market_data" file.
- **crypto_market_data.csv:** The csv file that contains the data of price fluctuations in the cryptocurrency market.

## Steps

1. **Load the Crypto Data:**
   - Convert and read the `crypto_market_data.csv` file as a DataFrame.
   - Check if the dataset is clean and consistent by displaying a sample of its data.

2. **Data Preparation:**
   - Standardize the data with `StandardScaler` to make sure all of the features have a similar scale.
   - Save the standardized data into a new DataFrame.

3. **Best Value for `k` (Elbow Method):**
   - Use the Elbow Method to find the best value of `k` for K-means clustering.
   - Loop through possible `k` values, from a range of 1 to 11, and compute the inertia for each value.
   - Plot a line chart with all the inertia values and locate the "elbow point" in the graph to select the optimal `k`.

4. **Clustering with K-means (Original Scaled Data):**
   - Initialize and fit the K-Means model using the best value for `k`.
   - Predict the clusters and add them as a new column as cluster labels.
   - Identify the clusters by vizualizing them with a scatter plot.

5. **Optimize Clusters with Principal Component Analysis (PCA):**
   - Use the PCA model to reduce to three principal components.
   - Calculate the total explained variance by adding the variance percentages of each principal component together.

6. **Best Value for `k` (PCA Data):**
   - Repeat the Elbow Method with the PCA data to find its best `k`.
   - Plot a line chart with all the inertia values and locate the "elbow point" in the graph to select the optimal `k`.

7. **Clustering with K-means (PCA Data):**
   - Initialize and fit the K-Means model, with PCA Data, using the best value for `k`.
   - Predict the clusters and add them as a new column in the PCA DataFrame.
   - Identify PCA Data's clusters by vizualizing them with a scatter plot.

8. **Calculate Feature Weights on each Principal Component:**
   - Create a DataFrame to find the weights of each feature on the principal components.
   - Calculate the strongest positive and negative influences, on each component, to find key drivers of fluctuations in the data.

## Summary
- With the Elbow Method, we found that the optimal number of clusters for this cryptocurrency data is 4. This applies in both the original and PCA-transformed data.
- Optimizing the clusters with PCA revealed that 89.5% of the data’s total variance is explained by the top three components.
- The clustering analysis concludes with finding the features with the strongest influence, for each PCA. They are "price_change_percentage_200d", "price_change_percentage_30d", and "price_change_percentage_7d".
