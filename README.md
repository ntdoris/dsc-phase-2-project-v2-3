# Phase 2 Project - Natalya Doris

## Project Overview

In this project, I use multiple linear regression modeling to analyze house sales in a northwestern county.

### Business Problem

Real estate company Royal Homes is looking to better understand the King County housing market before they finalize their business strategy. We seek to answer the following questions: what types of homes should they be looking to sell to make the most profit? What features lend towards higher sale prices?

### Data Understanding

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this GitHub repository. 

The data contains the following columns:

* 'bedrooms': number of bedrooms
* 'bathrooms': number of bathrooms
* 'floors': number of floors (levels) in the house
* 'waterfront': whether the house is on the waterfront
* 'view': quality of view from house
* 'condition': how good the overall condition of the house is; related to maintenance of house.
* 'grade': overall grade of the house; related to the construction and design of the house
* 'zipcode': zip code
* 'sqft_living': sq. ft. of living space
* 'sqft_lot': Square footage of the lot
* 'sqft_above': Square footage of house apart from basement
* 'yr_built': year house was built
* 'sqft_living15': sq. ft. of interior housing living space for the nearest 15 neighbors
* 'sqft_lot15': sq. ft. of the land lots of the nearest 15 neighbors
* 'mth_sold': month house was sold
* 'yr_sold': year house was sold
* 'renovated': whether a house had a year populated in the yr_renovated column
                    

### Modeling

After three iterations, the final model includes log transformed sqft_living, and categorical/dummy variables for condition, view, zipcode, and waterfront. The dependent variable, price, is also log transformed.

While it is not perfect, it shows remarkable improvement in terms of normality of residuals, homoscedasticity and linearity while maintaining a similar R^2 as the second model. Around 85 percent of the variation in price is explained by the model. Skew of 0.053 is the closest we have seen to 0 thus far, and the kurtosis value of 4.86 is the lowest we've seen thus far. The final model also passes multicollinearity checks.

![image](https://user-images.githubusercontent.com/102126161/182182330-6ada51c0-b1ee-4142-b7c8-da4f8e16218e.png)
![image](https://user-images.githubusercontent.com/102126161/182182352-2d60271d-7580-407b-89ab-4e151ccf131c.png)
![image](https://user-images.githubusercontent.com/102126161/182182377-81b7eca4-d2d4-49b7-ab89-6722af7ccff8.png)


### Regression Results

![Screen Shot 2022-08-01 at 10 19 05 AM](https://user-images.githubusercontent.com/102126161/182182534-ec57f33d-75cf-42ba-ac9b-48094cec59cd.png)

In the final model we can see that a house's zip code is highly influential on its sale price given the magnitude of the coefficients of several zip codes, all of which are statistically significant. For example, a house in zip code 98039 is associated with a natural log of sale price that is 1.50 higher, or a price that is about ~4.48 dollars higher.

Square footage of a house's living space also positively impacts sale price. Given a 0.68 coefficient, a 1 percent increase in sqft_living increases price by 0.68 percent.

Whether a house is on the waterfront, the quality of view, and how good the condition of the house is also impact sale price. A waterfront property is associated with a log of sale price that is 0.45 higher, or a sale price that is 1.57 dollars higher.

![Screen Shot 2022-08-01 at 10 20 11 AM](https://user-images.githubusercontent.com/102126161/182182575-549d1133-f97d-4d0b-8c96-50461b81783b.png)

### Conclusion

Given the regression results, I would recommend the following:

* Focus on finding properties in advantageous zip codes 
* Focus on larger houses, particularity with a larger living space
* Waterfront properties and properties with good views tend to yield higher prices
* Condition matters. Selecting a house in poor condition can detract from sale price

### Repository Structure
* [Data](https://github.com/ntdoris/dsc-phase-2-project-v2-3/tree/main/data)
* [Notebook](https://github.com/ntdoris/dsc-phase-2-project-v2-3/blob/main/student.ipynb)
* [Presentation](https://github.com/ntdoris/dsc-phase-2-project-v2-3/blob/main/presentation.pdf)
