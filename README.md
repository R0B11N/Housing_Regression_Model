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

----

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

----

# Data

For our data, I used this dataset from Kaggle (https://www.kaggle.com/competitions/house-pricesadvanced-regression-techniques/data) which includes the test, train, and sample submissions CSV files.

----

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

----

# Reading and Inspecting the Data
```python
## Read The Training and Test Sets, Obtain All The Row and Column Data
test <- read_csv("test.csv")
## Rows: 1459 Columns: 80
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## chr (43): MSZoning, Street, Alley, LotShape, LandContour, Utilities, LotConf...
## dbl (37): Id, MSSubClass, LotFrontage, LotArea, OverallQual, OverallCond, Ye...
##
## i Use ‘spec()‘ to retrieve the full column specification for this data.
## i Specify the column types or set ‘show_col_types = FALSE‘ to quiet this message.

train <- read_csv("train.csv")
## Rows: 1460 Columns: 81
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## chr (43): MSZoning, Street, Alley, LotShape, LandContour, Utilities, LotConf...
## dbl (38): Id, MSSubClass, LotFrontage, LotArea, OverallQual, OverallCond, Ye...
##
## i Use ‘spec()‘ to retrieve the full column specification for this data.
## i Specify the column types or set ‘show_col_types = FALSE‘ to quiet this message.

sub_test <- read_csv("sample_submission.csv")
## Rows: 1459 Columns: 2
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## dbl (2): Id, SalePrice
##
## i Use ‘spec()‘ to retrieve the full column specification for this data.
## i Specify the column types or set ‘show_col_types = FALSE‘ to quiet this message.

```
----

# Validate Structure of the Data Sets, and Output Them As Data.
```python
head(train, 20)
head(test, 20)
str(data)
## Truncated To Save Space.

## Checking To See Missing Data Values, and Splice the Code For Missing Values
sum(is.na(test))
## [1] 7000

sum(is.na(train))
## [1] 6965

NA_values_test=data.frame(NA_value=colSums(is.na(test)))
NA_values_train=data.frame(NA_value=colSums(is.na(train)))
```
----

# Boxplot and Histograms
```python
# Box
boxplot(train$SalePrice, col = "red")
```
![alt text]((https://media.discordapp.net/attachments/906212540021895178/1104987989718868019/image.png?width=669&height=324)
