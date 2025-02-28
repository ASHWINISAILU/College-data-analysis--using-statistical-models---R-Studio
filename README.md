Analysis of College data using statistical models - Linear Regression/Multiple Linear Regression /ANOVA
1. Introduction

This report presents an analysis of the "College.csv" dataset using R programming. The dataset consists of various attributes of colleges, including enrollment, expenses, student-faculty ratios, and graduation rates. The study employs exploratory data analysis and linear regression modeling to derive insights into the factors influencing graduation rates.

2. Data Exploration and Preparation

2.1 Reading and Checking the Data

The dataset was loaded using the read.csv() function, and its dimensions were checked using the dim() function. The dataset comprises 775 observations and 17 variables.

2.2 Generating a Random Subset

A subset of 700 observations was extracted using the sample() function with a predefined random seed (2310158). The summary statistics revealed that the subset contained 507 private and 193 public universities. Additionally, 67 universities were classified as Elite, while 633 were non-Elite.

2.3 Visualization of Key Variables

Histograms were plotted for four numerical variables:

Outstate Tuition Fees

Room and Board Fees

Book Costs

Personal Expenses

These visualizations provided an overview of the distribution of financial aspects across institutions.

Histogram Graphs:

![image](https://github.com/user-attachments/assets/973fcfb4-1277-419b-b8af-2435ee9328a9)



![image](https://github.com/user-attachments/assets/4a49f771-ba74-426a-b27c-cf551462c2b5)



![image](https://github.com/user-attachments/assets/9b8b6d00-6f87-40e2-b214-c9766b6fa217)



![image](https://github.com/user-attachments/assets/d9f200fe-e47e-44e3-b985-d429577c830d)



3. Linear Regression Analysis

3.1 Simple Linear Regression

A simple linear regression model was fitted with Grad.Rate as the dependent variable and Private and Elite as independent variables:

![image](https://github.com/user-attachments/assets/2816e753-de09-4bcb-abf0-5f942a60c5b3)


![image](https://github.com/user-attachments/assets/91c12491-bfa1-4f8f-9f94-9e6f2bfc20d9)



•Residual Standard Error: 15.32

•Multiple R-Squared: 0.199 (19.9% of variance explained)

•Adjusted R-Squared: 0.1967

•F-statistic: 86.57, p-value < 2.2e-16

**Interpretation:**

Both Private and Elite variables significantly impact the Grad.Rate.

The model explains 19.9% of the variance in graduation rates.

The p-values for all coefficients are highly significant (p < 0.001), confirming their strong predictive ability.

The Adjusted R-Squared value is slightly lower than R-Squared, indicating minimal overfitting.

3.2 Confidence Intervals and Prediction Intervals

The 95% confidence intervals for the regression coefficients were calculated:

![image](https://github.com/user-attachments/assets/0073315a-2a05-4bc4-a9a2-9ea7faed9b87)


A prediction interval for a new data point (Private = "Yes", Elite = "No") yielded an estimated graduation rate of 66.49%, with an interval range of 36.37% to 96.61%.


3.3 Multiple Linear Regression

An extended model was developed incorporating all variables as predictors. This model aimed to improve the explanatory power of the regression.

![image](https://github.com/user-attachments/assets/a842f866-9d42-4475-a3f4-0d311b76976c)



Key Statistics:

Adjusted R-Squared: Increased from 0.1967 (simple model) to a higher value

F-statistic: Demonstrated a significantly lower p-value, indicating model improvement


ANOVA Test: Comparing the simple and multiple regression models showed that the extended model had significantly higher explanatory power.

![image](https://github.com/user-attachments/assets/7d1cb72e-4788-41d9-85b9-28cd8c7daca6)

The above ANOVA table helps us to predict the better model for this analaysis.Model 1 analyse the response variable Grad.Rate with two predictors Private and Elite. where as Model 2 analyse the response variable
with Grad.Rate with all predictors in the data set.

The Residual Degree of Freedom for model1 is 697 and model 2 is 683.The Residual Sum of Squares for model 1(163673) is higher than model 2(110622).Model 2 has sum of squares is 53051 which indicates the
variability with multiple predictors when compared to model 1.

The F-Satistics is 23.396 shows significant improvement in fit of model 2 when compared to model 1. The p-value is very low which shows statistically high significant for model 2 when compared to model 1.

This ANOVA table shows Model 2, with all predictors shows significantly better than model 1(where Private and Elite are the predictors). The lower RSS value of model 2 with more number of
predictors shows that predictors contribute significantly on variation in the Grad. Rate. Hence, the model 2 provides a better fit than model 1.


Conclusion: The multiple regression model outperforms the simple model, as indicated by a higher Adjusted R-Squared and ANOVA test results.


3.3.1 Fitting of Multiple Regression model

![image](https://github.com/user-attachments/assets/1f0dbe56-74f3-47ab-9964-aca0b75983a7)


![image](https://github.com/user-attachments/assets/d86c73d6-6fc5-4ce0-af83-6345d8fe1c19)


![image](https://github.com/user-attachments/assets/29e7fdef-ab93-49c6-9380-504d613afe33)


![image](https://github.com/user-attachments/assets/ad10e0f9-b5cb-4b5d-a3e7-608d072cf303)



The above four graph plots are explained below:
1.** Residuals Vs Fitted: **The plots are scattered randomly around zero points. Also, the red line is almostnear the zero point dotted lines which depicts that Grad. Rate is dependent on all other predictors.
   
2.** Q-Q Residuals:** This Quantile-Quantile point helps to check the normality of predictors. The pointsalmost fall on the diagonal line, however towards the end, there is a slight variation which shows that
variables are not fit on this model. By removing these the multiple regression fitting can be improved.

3.** Scale-Location Plot: **The plots are randomly scattered near the red line area. Some plots are scattered far away from the red line which represents that there are few unequal variables in residuals.

4. **Residuals vs Leverage:** This graph clearly shows the high influencing predictors among all other predictors concerning the leverage of Grad.Rate.There are a few plots that are scattered far away in the
graph which clearly shows that some variables have low variance. The high value of residual and leverage will clearly show their influence on this multiple regression model.

By conclusion from the above graph, the different plots clearly show us the highly influential variables, and assumptions on the regression model and determine the reliability of the model.


4. Conclusion

The dataset was successfully explored, and a random subset was analyzed.

The Private and Elite status of universities significantly influence graduation rates.

The multiple regression model provided a better fit than the simple model.

ANOVA confirmed that adding more predictors improved model performance.

This analysis demonstrates the importance of financial and institutional characteristics in influencing graduation rates, aiding policymakers in strategic decision-making.
