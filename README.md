# Crypto Clustering Challenge

## Project Overview

The goal of this project is to develop a machine learning model that will accurately determine which emails are spam. There will be two different classificiation models that each have their own methods of predictions; the logistic regression model and a random forest model. The most successful model would be able to create a more consistent email filtering system just by evaluating the pattern of spam emails.

## Installation Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ezwang8/classification-challenge.git
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

   - Install `scikit-learn` for machine learning models:
     ```bash
     pip install scikit-learn
     ```

5. **Navigate to the Project Directory:**
   ```bash
   cd classification-challenge
   ```

6. **Launch Jupyter Notebook:**
   Open the notebook interface:
   ```bash
   jupyter notebook
   ```

7. **Open the Notebook:**
   In Jupyter, locate the `spam_detector.ipynb` file and run the cells for analysis.

## Steps

1. **Retrieve the Data:**
   - Convert and read the data from `https://static.bc-edx.com/ai/ail-v-1-0/m13/challenge/spam-data.csv` into a dataset.

2. **Data Preparation:**
   - Split the Data into Training and Testing Sets with random_state = 78.
   - Use `StandardScaler` to scale the features data.

3. **Create and Fit a Logistic Regression Model:**
   - Train the Logistic Regression model with random_state = 1.
   - Fit the Logistic Regression model by using the test data.
   - Calculate the accuracy score by evaluating `y_test` vs. `testing_predictions`.

4. **Create and Fit a Random Forest Model:**
   - Train the Random Forest model with random_state = 1.
   - Fit the Random Forest model by using the test data.
   - Calculate the accuracy score by evaluating `y_test` vs. `testing_predictions`.

## Summary
- Between the two models, the Random Forest model would be more reliable for spam detection. The Random Forest model's accuracy score is 3% higher than the Logistic Regression model.
- If the Random Foresting model were to be used to detect spam, it will be able to be successful at a rate of 95.48%.
