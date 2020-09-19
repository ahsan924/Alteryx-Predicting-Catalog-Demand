# Predicting-Catalog-Demand-in-Alteryx

<img src="images/workflow.png">

## Step 1: Business and Data Understanding 
#### 1. What decisions needs to be made?
a. As the model depicts and the analysis on the data supports the decision of mailing the catalog out to the new customers with the expected profit from these 250 new customers be around $21,987.43 which exceeds the minimum target profit of $10,000.
#### 2. What data is needed to inform those decisions?
a. While our target is ‘Avg_Sale_Amount’ that needs to be predicted, two of the predictor variables ‘Customer_Segment’ and ‘Avg_Num_Products_Purchased’ are highly significant for predicting the final value.
b. Another important data needed was the cost of printing and distribution i.e. $6.5 of each catalog and the average gross margin of 50%.

## Step 2: Analysis, Modeling, and Validation 
(Important: Use the p1-customers.xlsx to train your linear model.)
#### 1. How and why did you select the predictor variables in your model? You must explain how your continuous predictor variables you’ve chosen have a linear relationship with the target variable. Please refer back to the “Multiple Linear Regression with Excel” lesson to help you explore your data and use scatterplots to search for linear relationships. You must include scatterplots in your answer.
a. The predictor variables in the model have been chosen based on the p-values that proves their significance and relationship with the target variable, as shown below;

<img src="images/most_coefficients.png">

b. Also the graphical illustration for all the variables taken into consideration in the above figure are as;

<img src="images/customer_ID vs. Score.png">
<img src="images/Customer_Segment vs. Score.png">
<img src="images/Score vs Avg.Prod_Purchased.png">
<img src="images/Store_number vs. Score.png">
<img src="images/zip vs, score.png">

#### 2. Explain why you believe your linear model is a good model. You must justify your reasoning using the statistical results that your regression model created. For each variable you selected, please justify how each variable is a good fit for your model by using the p-values and R-squared values that your model produced.
a. “Customer_Segment” and “Avg_Num_Products_Purchased” have the values lower than 0.05 and are contributing the most. Whereas, one other variable “Responded_to_Last_Catalog” is not present in the “p1-mailinglist” and we will not take it into consideration because that will cause error in the score when the model will be applied on to this dataset for prediction. So, two of the predictor variables are as shown below;

<img src="images/final_coefficients.png">

b. R-Squared value is almost 0.84 which is not very high but still more than 80%, whereas, the P-values for the selected predictors are very low which makes the predictive model sufficient.

#### 3. What is the best linear regression equation based on the available data? Each coefficient should have no more than 2 digits after the decimal (ex: 1.28)

Y = 303.46 – (Customer_SegmentLoyalty Club Only) * 149.36 + (Customer_SegmentLoyalty Club and Credit Card) * 281.84 – (Customer_SegmentStore Mailing List) * 245.42 + 0 * (Customer_SegmentCredit Card Only) + Avg_Num_Products_Purchased * 66.98

## Step 3: Presentation/Visualization

#### 1. What is your recommendation? Should the company send the catalog to these 250 customers?
Yes, as the model predicts the expected profit is higher than the set target of $10,000 as a profit.

#### 2. 2. How did you come up with your recommendation? (Please explain your process so reviewers can give you feedback on your process)
The expected profit of almost $22,000 is predicted based on a built model with two predictor variables as “Customer_Segment” and “Avg_Num_Products_Purchased” as these two are the most significant with very low P-values. Overall, the model’s Adjusted R-Squared value is almost 0.84 which shows the model is efficient.

#### 3. What is the expected profit from the new catalog (assuming the catalog is sent to these 250 customers)?
The expected profit from the new catalog is $21,987.43 which is after applying the 50% average gross margin and subtracting the cost of printing and distribution i.e. 1,625 = 6.5 * 250.