# Exploratory Data Analysis Telco Customer Churn

In this directory i'm doing exploratory data analysis to house_price.csv.

## Preparations

```{r}
library(ggplot2)
library(dplyr)
library(ggcorrplot)
dfori = read.csv('https://raw.githubusercontent.com/dhykac/House-Price-Advanced-Regression/main/house_price.csv')
```

## Objectives

The main question of the topic is :
1. How the analysis of the target feature ['SalePrice'] ?
2. What are the top 5 strongest correlation to the target feature?
3. Test the statement that said low ['OverallQual'] will decrease the ['SalePrice'] , on the contrary high ['OverallQual'] could rise the ['SalePrice']!
4. Also , prove the statement that new builded house (latest ['YearBuilt']) most likely had high ['SalePrice']
5. If you do scatter plot with ['GrLivArea'] and ['SalePrice'] you could find that there are two houses with high ['GrLivArea'] but low ['SalePrice']. Analyze these two 'haunted house'!
6. Do freestyle EDA and find one interesting insight!

## Results Preview

From the analysis, we found that :

1. The insights we could find at initial EDA is :
* The cheapest house price in Boston is 34900, and the most expensive is 755000.
* Average house price is 180291.
* Median of the house price is 163000.
* No missing values, which means the house data is the after-sold data not an estimated data.
* The distribution of ['SalePrice'] is right skewed, this is because of the average house price is higher than median house price.

2. From the analysis we know that :
* ['OverallQual'] had correlation 80% (0,8). This is make sense, because ['OverallQual'] is overall quality of the house that's mostly will affect house price.
* ['GrLivArea'] had correlation 70% (0,7). This also make sense, because ['GrLivArea'] is the habitual area from overall house. 
* ['GarageArea'], ['GarageCars'], ['FullBath'], ['1stFirSF'], ['TotalBsmtSF'] had correlation 60% (0,6). For ['GarageArea'], ['GarageCars'], ['FullBath'], and ['TotalBsmtSF'] still make sense because these four variables will affect house area, so the increased value of these four will increase the housing area and rise the ['SalePrice']. Then the variable ['1stFirSF'] still acceptable if another house had one floor, but rejected if another house refference had second basement.

![boxplot](https://user-images.githubusercontent.com/92696555/147419621-74293a40-da8e-4c65-81fa-0617168c1b51.png)
3. From the boxplot analysis, we could conclude that's right high ['OverallQual'] will rise ['SalePrice']

![1](https://user-images.githubusercontent.com/92696555/147419688-ba7797e6-cdb3-495e-8ca1-af666a3bdd47.png)
![2](https://user-images.githubusercontent.com/92696555/147419692-d1aa96fe-f432-4caa-9c16-4df844afa495.png)
![3](https://user-images.githubusercontent.com/92696555/147419693-ff31cba8-842c-4a2e-9e60-1408aec668a0.png)
![4](https://user-images.githubusercontent.com/92696555/147419694-a3736d91-9c5a-4168-bb5f-9ba1d2d293f8.png)
4. From the analysis above, we could conclude that's new ['YrBuilt'] also had high ['SalePrice'] . This because ['OverallQual'] had high positive correlation (0,8) with  ['SalePrice'] (which is new house surpass old house), but ['OverallCond'] stucked and even most likely decrese due to negative correlation (-0,1).

5. Because the house still had ongoing construction process. The house with ['GrLivArea'] 4672 have ['YrBuilt'] and ['YrSold'] at 2017 but still had ['YrRemodAdd'] at 2008 which is mean the house still remodeled until 2018, on the other side the house with ['GrLivArea'] 5642 have ['YrBuilt'], ['YrSold'], ['YrRemodAdd'] at same year which is mean the house built, sold, and remodeled at same year. You could also see this on ['SaleCondition'] that said partial , means the house still had ongoing process.

![freestyle](https://user-images.githubusercontent.com/92696555/147419948-97de3a39-1873-49f0-808e-117a539b3cd4.png)
6. From the plot above, we could say that :
* The outlier house had wide area but lack of habitual space (only 2036) .
* That implied, house with wide property area will useless if had small habitual area (relate with correlation between ['GrLivArea'] and ['SalePrice'].
