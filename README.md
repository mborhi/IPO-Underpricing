# Predicting Short-term IPO Returns 
For our final project, we developed models to predict the underpricing of IPOs or Initial Public Offerings. By collecting previous IPO data, we were able to train multiple AI and machine learning models to classify the data. Our best model, a Random Forest algorithm, achieved an accuracy of about 76%. All of our development was done in python using Jupiter notebooks.

## Table of Contents 

- [Installation](#installation)
  - [Libraries](#libraries)
  - [Dependencies](#dependencies)
- [Data Collection](#data-collection)
- [Features](#features)
- [Models](#models)
- [References](#references)

# Installation 

### Libraries 
The libraries we used include:
- `scikit_learn:` Used for training and classifying with our selected models as well as for analyzing the results.
- `pandas:` Used for general data handling, especially importing and combining data from csv files.
- `numpy:` Used for general data formatting and handling.
- `pytorch:` Used to create a Binary Classification Neural Network.
- `seaborn:` Visualization.
- `ipython:` Development environment.

### Dependencies
To install all of our project dependencies run:
```
pip install -r requirements.txt
```

# Data Collection
For data collection and formatting we used `pandas` and `.csv` files. All of our data can be found in the [data](/data) folder and each source that needed to be cleaned has an independent ipython notebook in the [cleaning_scripts](/cleaning_scripts) folder. The following websites and applications are where we sourced our data for the project. 

- **IPOScoop Data:** 
  - Source: [IPOScoop.com](https://www.iposcoop.com/scoop-track-record-from-2000-to-present/)
  - Notebook: [scoop-data.ipynb](/cleaning_scripts/scoop-data.ipynb) 
  - We converted the `.xls` file into a `.csv` file in the cleaning file. 
  - IPOs from `2000` to `2020`.
- **Ticker Data:**
  - Source: [Ticker.com](https://ticker.com/IPO-Pricing)
  - Notebook: [ticker-data.ipynb](/cleaning_scripts/ticker-data.ipynb)
  - Scraped directly from the website using pandas `read_html` function. 
  - Concatenated data from `2012` to `2022`.
- **Bloomberg Data:** 
  - Source: [Bloomberg Terminal](https://en.wikipedia.org/wiki/Bloomberg_Terminal) 
  - Notebook: [bloomberg-sector-cleaning.ipynb](/cleaning_scripts/bloomberg-sector-cleaning.ipynb)
  - Downloaded datat from computer access in the business library. 
- **FRED Data:**
  - Source: St. Louis [Federal Reserve Economic Data](https://fred.stlouisfed.org/) database.
  - Used to source macroeconmic data on a specific industry and sector.

# Features

We train all our models using the following features:

- Sales - 1 Yr Growth
- Profit Margin
- Return on Assets
- Offer Size (M)
- Shares Outstanding (M)
- Offer Price
- Market Cap at Offer (M)
- Cash Flow per Share
- Instit Owner (% Shares Out)
- Instit Owner (Shares Held)
- Real GDP Per Capita
- OECD Composite Leading Indicator
- Interest Rate
- Seasonally Adjusted Unemployment Rate
- CPI Growth Rate
- Industry Sector
- Industry Group
- Industry Subgroup
- Underpriced (Classifying Feature)

These features were selected based on the features used in previous research, along with the data that was publically available to us. Please reference our research paper for a definition of each feature.

# Models
We implemented four machine-learning models that were identified by previous research done in the field. We utilized the `sklearn` library to implement the random forest, gradient boosting classifier, and support vector machine. We used the `pytorch` library to implement a neural network. All of our models can be found in the [models](/models) folder.

- **Random Forest:**
  - Notebook: [random_forest_scikit.ipynb](/models/random_forest_scikit.ipynb)
  - Overall Accuracy: 76%
    - Underpriced Accuracy: 92.8%
    - Overpriced Accuracy: 16.6%
  - Implemented using the `sklearn` function `RandomForestClassifier`
- **Gradient Boosting Classifier:**
  - Notebook: [gradient_boosting.ipynb](/models/gradient_boosting.ipynb)
  - Overall Accuracy: 75.3%
    - Underpriced Accuracy: 94.9%
    - Overpriced Accuracy: 12.1%
  - Implemented using the `sklearn` function `GradientBoostingClassifier`
- **Support Vector Machine:**
  - Notebook: [svm.ipynb](/models/svm.ipynb)
  - Overall Accuracy: 73.9%
    - Underpriced Accuracy: 100%
    - Overpriced Accuracy: 0%
  - Implemented using the `sklearn` function `svm`
- **Neural Network:**
  - Notebook: [neural_network.ipynb](/models/neural_network.ipynb)
  - Overall Accuracy: 70.2%
    - Underpriced Accuracy: 88.8%
    - Overpriced Accuracy: 16.2%
  - Implemented using `pytorch` library


## Random Forest Model Configuration
To achieve a 76% accuracy for the random forest model, we first anaylized several of the model's parameters. Specifically, examined the results of every combination of the features listed below:

* _estimators_ - The number of trees in the forest 
* _criterion_ -  The function to measure the quality of a split
* _max_depth_ - The maximum allowed depth for trees
* _max_features_ - The number of features to consider in each tree

After analysis, the `max_depth` of the tree turned out to be the determining factor in a model's accuracy. The full process can be found in the [test_random_forest_model_config.ipynb](/models/test_random_forest_model_config.ipynb). 

# Final Project Paper
  For more information view our [project paper](/B351_Main_Project_Final_Paper.pdf). It goes into much greater detail about our problem space, algorithms, methods, and results.

# References

### Research Papers
- [Predicting IPO underperformance using machine learning](https://www.researchgate.net/publication/356616690_Predicting_IPO_underperformance_using_machine_learning) by Rachit Agrawal

- [Textual Information and IPO Underpricing: A Machine Learning approach](https://mpra.ub.uni-muenchen.de/103813/1/MPRA_paper_103813.pdf) by Apostolos Katsafados et al.

- [A Neural Network Model to Predict Initial Return of Chinese SMEs Stock Market Initial Public Offerings](https://ieeexplore.ieee.org/document/4525247) by Dan Meng

- [Proceedings of the 2021 3rd International Conference on Economic Management and Cultural Industry](https://www.atlantis-press.com/proceedings/icemci-21/125965936) by Kelai Wang

### FRED Data
- [International Monetary Fund, Interest Rates, Discount Rate for United States](https://fred.stlouisfed.org/series/INTDSRUSM193N)

- [Organization for Economic Co-operation and Development, Consumer Price Index: Total All Items for the United States](https://fred.stlouisfed.org/series/CPALTT01USM657N)

- [Organization for Economic Co-operation and Development, Leading Indicators OECD: Leading indicators: CLI: Normalised for the United States](https://fred.stlouisfed.org/series/USALOLITONOSTSAM)

- [U.S. Bureau of Economic Analysis, Real gross domestic product per capita](https://fred.stlouisfed.org/series/A939RX0Q048SBEA)

- [U.S. Bureau of Labor Statistics, Unemployment Rate](https://fred.stlouisfed.org/series/UNRATE)

- [Share of IPOs with negative first day earnings per share (EPS) in the United States from 1980 to 2021](https://www.statista.com/statistics/429868/share-of-ipo-deals-with-negative-first-day-return-usa/)


