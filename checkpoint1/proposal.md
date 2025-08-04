## Title : Corn Crop Production Prediction in Iowa using machine learning techniques

## Team
- **Heeyoon Shin (POC)**: hshin17@syr.edu
- **Sindy Siddarth Reddy Kolli**: sikolli@syr.edu
- **Mohamed Elbaz**: moabdall@syr.edu
- **Kenny Lual** : kdlual@syr.edu

## Introduction
Corn is more than just a crop in Iowa. As one of the leading producers in the United States, Iowa's farmers rely on its rich soil and favorable climate. However, they face challenges from unpredictable weather, varying soil conditions, and market fluctuations. Accurate yield predictions are essential for farmers to plan their strategies and ensure food security for their communities.

Our approach integrates historical corn production data with biofuel trends and environmental factors, employing advanced machine learning techniques to enhance accuracy. This proposal seeks to leverage ML techniques to forecast corn yields in Iowa, empowering farmers and policymakers with actionable data to optimize their practices and promote sustainability in the face of a changing climate.

## Primary Stakeholder
The primary stakeholders in this project are Iowa's farmers, who depend on accurate corn yield predictions to make informed decisions about planting and resource allocation. Their economic viability and sustainability hinge on these forecasts. 

The other stakeholders are agricultural organizations and policymakers including government agencies, such as Dept. of Agriculture, which will use the insights generated to develop strategies that enhance food security and promote sustainable practices.

## Literature Review

The intersection of agriculture and machine learning has gained significant attention in recent years, particularly in crop yield prediction. While many studies have demonstrated the efficacy of machine learning techniques for forecasting crop production, few have adequately addressed the relationship between corn yields and biofuel trends.

Previous research often relies on regression models, Random Forest, and Gradient Boosting to analyze climate factors and their impact on crop yields. For instance, studies have shown how variables such as weather patterns and soil characteristics influence yields by examining their non-linear relationships[^1]. However, these studies typically overlook the critical role of biofuel markets and their fluctuations, which can significantly affect corn production decisions.

Moreover, the importance of feature selection and engineering in enhancing model performance has been emphasized. A study by Kumar demonstrated that incorporating indicators like soil health and climate forecasts significantly improved the predictive power of machine learning models[^2]. Ensemble methods have emerged as powerful tools in agricultural predictions, with studies indicating that combining multiple models can yield more robust predictions by leveraging the strengths of individual approaches[^3][^4]. Yet, the inclusion of biofuel consumption trends remains largely absent, despite its potential impact on corn demand and agricultural practices.

Overall, while existing research underscores the promise of machine learning in improving corn yield predictions, there is a significant opportunity to enhance these models by incorporating biofuel trends. By leveraging both historical and real-time data, including biofuel trend, our approach aims to empower farmers and stakeholders to make more informed decisions.

## References
[^1] : Liakos, K. G., et al. (2018). Machine learning in agriculture: A review. Sensors, 18(8), 2674.
[^2] : Kumar, A., et al. (2020). Feature selection for crop yield prediction: A review. Computers and Electronics in Agriculture, 175, 105612.
[^3] : Khatri, A., et al. (2021). Enhancing crop yield prediction using ensemble machine learning techniques. Agricultural Systems, 187, 102995.
[^4] : Zhao, X., et al. (2019). Data-driven approaches for predicting crop yields: A review. Agricultural Systems, 173, 23-30.

## Data and Methods
This project use Iowa's corn production from year 2015- 2020.

**Iowa Corn Production**

This project focuses on Iowa's corn production data from 2015 to 2020. The dataset is sourced from the USDA's National Agricultural Statistics, which contains a total of 52 million entries. For our analysis, we have narrowed this down to Iowa's yearly corn production, resulting in 576 relevant entries.

It's important to note that while the number of rows has been reduced, these entries represent different geographical locations across Iowa. Our analysis will explore the factors impacting corn production in various regions, including Central, East Central, North Central, South Central, West Central, Northeast, Southeast, Southwest, and Northwest Iowa.


- [2015-2020 Iowa Corn Production](https://quickstats.nass.usda.gov/#E9878150-9EAD-39CF-9D5A-D13587727DDC)

Number of rows: 576
Number of columns: 21


**Climate Dataset**

The second dataset is the [2015 - 2023 Iowa Climate Data](https://mesonet.agron.iastate.edu/request/coop/fe.phtml)
  dataset which contains climate data of Iowa for each region. There are nine different regions based on the data source: 
  West Central, East Central, Central, South West, South Central, South East, North West, North Central, North East. 
  This is coherent with our Iowa's corn production data.  

The key variables in this dataset are:
High Temperature [C] 
Low Temperature [C]
Precipitation (rain+melted snow) [mm]

Number of rows: 243 (27 * 9)
Number of columns: 14


**Biodiesel Dataset**

Biodiesel become a key energy source to the US after passing Energy Policy Act of 1992. Also, corns are used as source of biofuel. 
We have found a dataset from US Dept. of Agriculture for monthly average price for biodiesel and diesel in the US. We will subset the data
from 2015 to 2020 for our further analysis. 

- [1994-2024 US Biodiesel & diesel Monthly Average Price](https://www.ers.usda.gov/data-products/u-s-bioenergy-statistics/)

Number of rows: 365,
Number of columns: 4


**Other Dataset**
In addition to the climate dataset, we are also interested in understanding the soil conditions for each region in Iowa. However, we have not yet identified a relevant dataset to incorporate into our analysis. Also, we are looking other possible data that can be explanatory variables for Iowa's corn production for each year. Here are some possible key factors we believe are important.

## Other Factors Influencing Corn Productions
1. Soil Condition (Monthly)
2. Usage of Pesticides (Monthly)
3. Iowa's population growth rate (Monthly)
4. Corn Market conditions and prices


### Methods
Data Integration:
Aggregate the corn production and other explanatory variables.

Data Preprocessing:
Clean the dataset by removing any redundant columns and handling missing values appropriately.
Standardize numerical features to ensure consistency in scale across variables.
Encode categorical variables (e.g., region) using one-hot encoding for compatibility with machine learning models.

Machine Learning Models:
Implement various machine learning algorithms, including Linear Regression, Random Forest Regression, Gradient Boosting Machines, and Support Vector Regression, to analyze the impact of climatic and other variables on corn production.
Use cross-validation techniques to evaluate model performance and avoid overfitting.

Feature Importance Analysis:
Conduct feature importance analysis using methods like feature importance plots and correlation analysis to identify which variables most significantly affect corn yields.

Hyperparameter Tuning:
Employ grid search optimization to fine-tune model parameters, enhancing predictive accuracy.
    

### Project Plan

Period : Oct 9-18
Activity : Data Collect (for third and fourth dataset), EDA, Stakeholder Analysis 
Milestone : Completed stakeholder analysis and data exploration. Additional datasets identified as necessary.

Period : Oct 19-25
Activity : Data Preprocessing, Applications of simple ML Techniques
Milestone : Finalize the data cleaning and test simple ML techniques on our cleaned data

Period : Oct 25-Nov 3
Activity : Cross-Validation
Milestone : Established a robust cross-validation framework to evaluate model performance and ensure generalization.

### Risk
Because it is too early stage, we are not worried about technnical issues. However, there are couple risks we have noticed while preparing this project as a group:

1. Data Availability : Currently, we are still looking for other explanatory variables for our analysis, meaning that we may face difficulties in finding relevant data.
2. Model Performance : We are not sure whether our intution on this idea can be explained by ML techniques using our data.

