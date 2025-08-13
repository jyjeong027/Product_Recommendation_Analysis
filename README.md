# Project Overview
This project analyzes simulated customer behavior to determine whether giving more personalized product recommendations leads to higher customer spending, using linear regression. It also calculates the optimal number of recommendations by identifying the point of diminishing returns.

# Background 
Company A is a retailer offering both grocery and non-grocery products through a single loyalty app. The app provides customers with personalized product recommendations based on their browsing and purchase history to drive engagement and sales.

# Business Objective and Problem Definition :
**Objective**: Understand the impact of personalized product recommendations on customer purchasing behavior 

**Key Questions**:
- Does the **number of recommendations** influence the **total spend on recommended products**? 
  - Analyzed using Linear Regression: Among customers who made purchase, linear regression used to explore relationship between number of recommendations and total spend on products(continuous outcome)
- Should efforts be made to increase number of recommendations? 
- What is the optimal # of recommendations?

## Dataset
The dataset contains simulated customer-level data from a personalized recommendation program including:
- **Customer demographics**: age, income, location  
- **Recommendation features**: number of recommendations shown, previous engagement with recommendations, recommendation relevancy
- **Target variable**: total spend on recommended products (for purchasing customers only)

# Methodology 
1. **Data Preprocessing**
   - One Hot Encoding categorical features
   - Standard Scaling numerical features
2. **Linear Regression** (statsmodels.OLS for statistical insights) 
- Apply Lasso for feature selection (remove zero coefficient features)
- Check VIF Scores to check and drop multicollinear features
- Add intercept and squared term for number of recommendation capture nonlinear effects 
3. **Model evaluation** using (R-Squared, P values):

# Conclusion 
Based on the results: 
- Relevancy Score was the strongest predictor of total spend
- The number of recommendations had a positive effect on spending
- The negative coefficient on the squared term showed a diminishing return, indicating the impact of each additional recommendation decreased after a certain point
  - This inflection point was found to be 3 recommendations

**Final Recommendation** 
While increasing the number of personalized offers does lead to higher spending, the return diminishes after 3. 
Therefore, given the additional cost and effort required to generate more recommendations, Company A should **limit recommendations to 3** and instead **focus on improving the relevancy of recommendations**, as relevancy had biggest influence in total spending.
