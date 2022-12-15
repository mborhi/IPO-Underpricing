# Monkey AI Final Project

# Predicting Short-term IPO Returns

# Data
The Scoop data was gathered from a spreadsheet publicly available on IPOScoop.com at the following link: https://www.iposcoop.com/scoop-track-record-from-2000-to-present/

The Ticker data was gathered from a Ticker.com at the following link: https://ticker.com/IPO-Pricing

The Bloomberg data was gathered from the Bloomberg database using the terminal in the business library

Additional macroeconomic data was found on the St. Louis FED FRED database.

# Features

Currently we are planning to train our models using the following features:
* Sales - 1 Yr Growth
* Profit Margin
* Return on Assets
* Offer Size (M)
* Shares Outstanding (M)
* Offer Price
* Market Cap at Offer (M)
* Cash Flow per Share
* Instit Owner (% Shares Out)
* Instit Owner (Shares Held)
* Real GDP Per Capita
* OECD Composite Leading Indicator
* Interest Rate
* Seasonally Adjusted Unemployment Rate
* CPI Growth Rate
* Industry Sector
* Industry Group
* Industry Subgroup
* Underpriced (Label by which we are classifying data points)

These features were selected based on what features were used in previous studies along with what data was available to us.

# Models

We implemented our main random forest model using Scikit-learn. We have also implemented potential alternatives, such as a neural network, support vector machine, and gradient boosting model.

# Libraries

We used the following libraries:
  * Scikit-learn - Used for training and classifying with our selected models as well as for analyzing the results
  * Pandas - Used for general data handling, especially importing and combining data from csv files

# Components of the Project
The implementation of our main Random Forest model can be found in the Jupyter notebook, 'random_forest_scikit.ipynb', in the 'Models' folder of the 'Random Forest' branch. As outlined in the notebook, this model was trained using the dataset in the 'data' folder titled 'clean_bloomberg_with_sectors_macro.csv'. This file combined all of the IPO-specific and macroeconomic data by ticker for each IPO.

# How to install dependencies and build/run the project

