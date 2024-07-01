# **Business Understanding**

## Problem Statement


- The stakeholder for this project is a ***real estate investment firm*** seeking to construct residential homes in the United States that promise a high return on investment. This project entails performing a time series analysis on a Zillow dataset covering various locations across the country to identify these prime investment areas.
***Stake Holder:** The Bizzaro Real Estate Agency
***Objectives:**

*   Identify the top 5 zip codes for the real estate agency to invest in.
*   Forecast future house prices in these zip codes.
*   Provide insights and recommendations

# **Data Understanding**

The dataset used in this project comprises historical median house prices from various states in the USA, spanning from April 1996 to April 2018 (22 years). This data was obtained from the [Zillow website](https://www.zillow.com/research/data/).

The dataset contains 14,723 rows and 272 columns, with 4 categorical columns and 268 numerical columns.

#### Column Names and Descriptions:
- **RegionID**: Unique identifier for each region.
- **RegionName**: Names of the regions (zip codes).
- **City**: Names of the cities for the regions.
- **State**: Names of the states.
- **Metro**: Names of the metropolitan areas.
- **CountyName**: Names of the counties.
- **SizeRank**: Rank of zip codes by urbanization.
- **Date Columns (265 Columns)**: Median house prices across the years.

  ### EDA
1.
   ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/b40d3eac-9560-423d-be0a-58346ac9e36e)

  - Observations:The following states tend to have affordable houses ,  'TN' :Tennessee being the most affordable state in the states others include;
SD: South Dakota
OK: Oklahoma
OH: Ohio
IN: Indiana
IA: Iowa
AR: Arkansas
KY: Kentucky
ME: Maine
WV: West Virginia

2. * WHat are the  top 10 most expsensive states in terms of House prices?
     ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/1a2b8247-61aa-4e7c-adf7-dddcc62ecfe0)
-Observations: The following states tend to have expsensive houses.
 **NY (New York)**  has the highest median house price, around $600,000 followed by
 **HI (Hawaii)** ,
 **CA (California)** ,
 **DC (District of Columbia)**,
 **NJ (New Jersey)** ,
 **WA (Washington)**,
 **MA (Massachusetts)**,
 **IL (Illinois)** ,
 **VA (Virginia)** and
 **AK (Alaska)**

 3. What are the  top 10 most affordable cities in terms of House prices?
    ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/e43af5b4-f29c-49ee-a731-b90a3a7d9597)

    - Observations:Wilkes-Barre  is the cheapest city in terms of house pricing followed by
Jamestown       
Brownsville  ,
Cleveland  ,
Wilkinsburg  ,
Harlingen  ,
Granite City  ,
Pharr  ,
Reidsville and
Port Huron   .

*  The houses in this cities range from approximately 55000 to 72000
  
4. Which  top 10 cities have  the  most expensive houses?
![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/881a582f-e040-42f9-8b28-376b9f0ff325)


*   Observations:Burlingame is the most expensive city in the USA followed by;
Newport Beach
San Francisco
Menlo Park
Cupertino
Bellevue ,
Miami Beach ,
Hoboken ,
Rancho Palos Verdes and
Sunnyvale ,

*   The house prices in these citites range from  approximately1,501,827 dollars to 881,347 dollars

5.Yearly Trend of Median House Prices
![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/024ac448-d9fb-436c-a093-18d89e4ef42e)

- Observations:Initial Growth (1996-2007):

- There is a steady increase in median house prices from 1996 to around 2007.
The growth accelerates significantly from around 2000 to 2007.
- Following the peak, there is a notable decline in prices, bottoming out around 2012.
- From 2012 onwards, there is a consistent and steady increase in house prices up to 2020

6.Does urbanization  rank affect the average house prices?
![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/1154109a-01d9-4a77-93b6-715111cda6e9)

- Observations: Urbanisation has no effect on the house prices .

  7.*  What top 10 Zipcodes have the highest ROI?
  ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/5e8ac78d-0e8f-40e4-bf15-29fdeec4356b)

  8. ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/f6a3434a-57ef-4110-b600-35ce3721734e)
     
- The cities with the highest ROI(return on investement) are;
Sea Island,Glen Arbor,Zephyr Cove,Kilauea,Haiku,Shaver Lake,Sint Helena,Green port,Wainscott and Amagansett.<br>
- This information is valuable for real estate investors, developers, and policymakers seeking to make informed decisions and capitalize on growth opportunities in the housing market.
  
  9. **Top 10 Cities with the highest Risk factor(CV)**
  ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/305b8948-ecfe-4398-9d88-42a074dd7b28)

  A high CV means that  the price deviates further from the mean and  that there is presence of high price volatility making it a problem to effectively predict their future median house prices.This means that real estate investors cannot invest in these areas.<br>
The cities with the highest price volatility are:
*   Hanska
*   East Dublin
*   Saint Helena
*  Mineral City
*   Yellow springs
*  Axton
*  Pedro
* Martins Ferry
*   Glen Arbor
*  Spring Hill.

10. ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/abb9dbf9-15ba-49b0-8b3c-61e2201aff02)
    **observations:**

The Average house prices  keep on increasing however the prices remain constant between 1996 and 2004

11. Correlation analysis
![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/25c58958-7eb4-457b-a122-c2516f694385)

- The dataset does not exhibit multicollinearity
  ### **Time Series Ananlysis**

  - WE will focus on one zipcode  among the ones that have highest ROI in our TSA
    - **Baseline Model**

- We will use the ARIMA model as our baseline model.

  ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/79f628e9-7f97-4814-b875-a069869a3655)
- Forecast (Blue Line):
The blue line represents the forecasted values.
It appears relatively smooth, suggesting a model’s prediction over time.
-Actual (Green Line):
The green line represents the actual recorded values.
It is highly volatile, with sharp peaks and troughs.
-Problem in the Forecast:
The forecast fails to accurately predict extreme variations seen in the actual data.
At various points, the forecast underestimates or overestimates the actual values.
This discrepancy indicates that the forecasting model may not handle the data’s volatility effectively.


- SARIMA MODEL
  
- We saw that there is seasonality in the data, so the best model to use is one that also caters for seasonality-SARIMAX
  ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/f756318a-d770-4b93-9724-48a4d77b6e9f)
RMSE: 263342.52
the model performe quited well in forcasting the actual values
 - facebook prophet
   ![image](https://github.com/Dee-Olulo/Time-series-analysis/assets/151445934/8564a462-da59-457c-a68d-c92e3c7ea2ca)
 

