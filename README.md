## Introduction

For this project I will be using a dataset for real estate prices in King's County, Washington. I will be using the OSEMN model for processing, detailed below:

O - Obtain:
    This step involves importing data and all relevant libraries.
S - Scrub:
    During this step we will identify and fill null values and clean our data.
E - Explore:
    This step can be mixed with scrubbing.  Here we will investigate our data and look for patterns.
M - Model:
    Here we will use our data to build a model to predict our target variable.
N - iNterpret:
    Finally we will interpret the results of our model and communicate our findings to stakeholders.
    
My goal is to identify the best and worst factors in house sale prices for real estate listings in King's County. The data contains information on house prices, date of sale and descriptive features of the houses (number of bedrooms, number of bathrooms, sq. footage, etc). I will be using a multivariate linear regression to find the importance of each feature on house prices. For a deeper look at my code and analysis, check out the notebook in this repository.

## EDA 

Before modeling I looked at the interactions between some of the variables to see if there will be any correlation issues. First, I looked at the sqft_living and sqft_living15 columns. These represent the living space of each home and the average living space of a home's closest 15 neighbors. Neighborhoods tend to have similarly sized homes, so I expected high correlation between these two variables.

![](images/footage_vs_neighbors)

There is a definite correlation here, though a smaller effect than I expected. I will need to account for this correlation during modeling. To further investigate the relationship between each house and its neighbors I looked at the sqft_lot and sqft_lot15 columns which represent land lot size for a house and the average lot size for that house's neighbors.

![](images/Lotsize_vs_neighbors.png)

Here we see a very strong correlation. It seems that neighborhoods divide up land lots to be roughly the same size, even if the houses themselves are not. Finally, I wanted to look at look at how the waterfront and view columns interact. I expected that waterfront houses would generally have a better view.

![](images/waterfront_and_view.png)

As expected, waterfront seems to be one of the most determining factors for view.