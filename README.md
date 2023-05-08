### Housing Regression Model

## Clean R Project on a Regression Model Predicting Housing Prices

# Abstract
Machine learning and statistical regression models have become increasingly popular in predicting house
prices. With the vast amount of data available in the real estate market, machine learning algorithms
can extract patterns and relationships that may not be obvious to humans. By analyzing historical data
on factors such as location, size, and amenities, regression models can accurately estimate the value of
a property. These models can also incorporate external factors such as economic trends and changes in
demographics to further improve their accuracy. As the real estate industry continues to evolve, the use of
machine learning and statistical regression models is likely to become even more essential for accurate and
efficient property valuation, as conducted in this dataset from Kaggle, with Kansas City’s Housing Market.

# Introduction 

The contents of the data sets are primarily oriented on 21,598 Kansas City Homes as a singular CSV file
packaged with 2,919 homes used as training models for the statistical regression model under train.csv and
test.csv. Considered factors for analysis include: Date of Sale, Price, Bedrooms, Bathrooms, Living Room
Size, Lot Size, Waterfront, Directional Views, Condition (linear), Grade (linear), Square Footage Above
Ground, Square Footage at Base, Year Built, Year Renovated, Zipcode, Latitude, and Longitude.
By using R’s data cleaning tools, and statistical visualization, the goal of the project is to construct a
powerful and accurate KNN and Linear Regression model to analyze future potential housing trends, and
the fluidity of the housing market.
Completing the task at hand would result in understanding the effects some factors which are considered
in the regression model have on the future of home prices in Kansas City, where market analysis can have
statistical backing for houses in a 2.4 million inhabitant metropolitan area.

# Data

For our data, I used this dataset from Kaggle (https://www.kaggle.com/competitions/house-pricesadvanced-regression-techniques/data) which includes the test, train, and sample submissions CSV files.

# Loading Packages and Libraries

```python
library(tidyverse)
## -- Attaching packages --------------------------------------- tidyverse 1.3.2 --
## v ggplot2 3.3.6 v purrr 0.3.4
## v tibble 3.1.8 v dplyr 1.0.10
## v tidyr 1.2.1 v stringr 1.4.1
## v readr 2.1.2 v forcats 0.5.2
## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
## x dplyr::filter() masks stats::filter()
## x dplyr::lag() masks stats::lag()

library(corrplot)
library(ggplot2)
library(lubridate)
library(gridExtra)
library(caTools)
library(GGally)
```
