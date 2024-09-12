# Cafe-Reward-Program-Analysis
Data Analysis and Dashboard (Python and Tableau)

Link to Project Dashboards on Tableau Public: https://public.tableau.com/views/RewardAnalysis/RewardProgramAnalysis?:language=en-GB&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Project Overview

A café has run a test by sending different combinations of promotional offers to its existing reward members. The objective of this analysis was to identify key customer segments and develop data-driven strategy for future promotional messaging and targeting.
This project focuses on evaluating the effectiveness of promotional offers and understanding customer behaviour.

## Data Source

The data for this project can be found at https://www.mavenanalytics.io/data-playground.
The link for downloading zip archive: https://maven-datasets.s3.amazonaws.com/Cafe+Rewards+Offers/Cafe+Rewards+Offers.zip

 
## Approach

To achieve the objectives, I performed EDA using Python, and then created Tableau dashboards to visualize the results. The analysis was primarily focused on segmenting the customers based on their behaviour during the promotional month and evaluating the performance of the reward program. I developed two dashboards to reflect these insights: one for customer segmentation and the other for the reward program analysis.

## Data Cleaning and Preparation

The EDA stage of the project was crucial in preparing the data for further analysis and visualization. It included the following stages:

1.	**Data Type Handling and Conversion**
2.	**Unpacking Values from Dictionaries**. The column ‘value’ contained a dictionary where key details about transactions and rewards were stored. Using Python and its libraries these values were unpacked into separate columns which allowed perform further calculations more efficiently.
3.	**Offer ID Description**. Each offer had its ID, but the parameters (e.g. type, duration, difficulty, reward) were represented in separate columns. I created a description column for each offer ID, combining all the information about each type of offers. This enabled a more granular analysis of how different offers impacted customer behaviour.
4.	**Data Merging**. I used data merging to have the information about events of the reward program and the customer details in one dataframe.
5.	**Correlation Analysis**. To check the relationships between customer demographics and offer completion rates I checked the correlations between i) age and offers completed, and ii) gender and offers completed. No strong correlation was revealed.
6. **Outlier Detection**. During the analysis of customers’ demographics, it was discovered that there was an abnormal concentration of customers whose age was over 100. There were 2086 customers of the age 118. For all these customers, other demographic information, such as gender and income, was missing. This lack of corresponding data suggested treating the age of 118 as incorrect and representing missing data. Further investigation is required to avoid distortion in future analyses.
7.	**Creating A Subset of Transactions Associated with Offers**. Since one of the objectives was to analyze the effectiveness of the reward program, I created a separate dataset that included only transactions related to the promotional offer. This step was important for ensuring that the analysis focused solely on the impact of the promotional offers.


## RFM Analysis

To segment the customers, I used RFM (Recency, Frequency, Monetary) analysis method. This model allows to classify the customers based on three factors:
- Recency: how recently a customer made a purchase
- Frequency: how often a customer makes purchases
- Monetary: how much a customer spends

Using these criteria, the customers were divided into 8 groups, each representing different levels of engagement and profitability. These segments form the foundation for future promotional targeting and personalized marketing strategies.

## Visualization

The Tableau dashboards provide visualization for both customer segmentation and the performance of the reward program. These dashboards will allow stakeholders to:
- **Understand Customer Behaviour**. Depending on RFM segment, key metrics such as spending and frequency of transactions are visually represented. The dashboard also visualizes the customers’ behaviour depending on their income level and age. 
- **Evaluate Reward Program Success**. The dashboard tracks key metrics such as customer response rate, offer completion rate, and customer engagement with specific offers. 

![](https://github.com/MariaSozinova/Cafe-Reward-Program-Analysis/blob/main/assets/Reward%20Offer%20Dashboard.jpg)

![](https://github.com/MariaSozinova/Cafe-Reward-Program-Analysis/blob/main/assets/Customer%20Segmentation%20Dashboard.jpg)

## Key Findings

1.	**Customer Segment “Needs Attention” and “At Risk”**. A significant proportion of customers fall into these two groups. They show lower engagement levels and at risk of churn. This provides the marketing team with the opportunity to design retention strategies targeting these customers, possibly through personalized offers or engagement campaigns.  
2.	**Increase in Membership in 2017**. The data shows a notable increase in new members during 2017. With further investigation, it will be possible to identify the factors behind this increase and replicate the successful elements in current and future campaigns to drive membership growth. 
3.	**Reward Program Success**. The analysis confirms the reward program has been successful. Over 75% of customers who received offers completed them. And 44% of all offers were successfully redeemed. These metrics demonstrate the effectiveness of the reward system in engaging customers.
4.	**Discount Offers are the Most Popular**. Among the different types of offers, Discount offers (with a difficulty of 10$, a reward of 2%, and a duration of 10 days) had a higher completion rate. This indicates that the customers prefer straightforward discount incentives over other types of offers.  
5.	**Discount Offers are More Profitable**. In addition to being popular, discount offers also proved to be more profitable for the café. Net revenue (after rewards) from discount offers accounted for 21% of total revenue, compared to 14% from Buy-One-Get-one (BoGo) offers. This suggests that discount-based promotions could be more frequently used to maximize both customer satisfaction and revenue.

## Recommendations

- **Target At-Risk Segments**. Focus on retaining customers from the “Needs Attention” and “At Risk” groups by offering personalized and targeted promotions. This could improve overall retention rates and reduce churn.
- **Leverage Discount Offers**. Since discount offers proved to be both popular and more profitable, the café should consider concentrating more on such offers in future promotional campaigns.
- **Investigate 2017 Membership Growth**. Conduct a deeper analysis of the factors that drove the increase in membership in 2017. Replicating these factors can enhance future membership growth strategies.
- **Optimize Offer Timing and Difficulty**. Based on customer behaviour, adjusting the difficulty (the amount to be spent by a customer to redeem the offer) and duration of offers could be further required to increase participation.
