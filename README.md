# Monkey AI Final Project

# Predicting Short-term IPO Returns

# Data
The Scoop data was gathered from a spreadsheet publicly available on IPOScoop.com at the following link: https://www.iposcoop.com/scoop-track-record-from-2000-to-present/

The Ticker data was gathered from a Ticker.com at the following link: https://ticker.com/IPO-Pricing

The Bloomberg data was gathered from the Bloomberg database using the terminal in the business library


# Features

Currently we are planning to train our models using the following features:
  * Offer and Opening price
  * Price range
  * Industry Sector
  * Offer Size/Oustanding Shares
  * Market Cap
  * Underwriter/Underwriter ranking
  * Venture Capital Backed

These features were selected based on what features were used in previous studies along with what data was available to us. We may add to or remove from this list depending on if we are able to find additional data, but this is our tentative list.

# Models

We have begun implementing the random forest model using Tensorflow.

# Libraries

We are using the following libraries so far:
  * TensorFlow - Used for training and classifying with our selected models as well as for analyzing the results
  * Pandas - Used for general data handling, especially importing and combining data from csv files

