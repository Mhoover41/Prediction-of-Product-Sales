# **Prediction of Product Sales**
- **Author:** Melissa Hoover
- **Email:** Hoovermissy@yahoo.com
- **LinkedIn:** https://www.linkedin.com/in/melissajhoover/

![food image](https://user-images.githubusercontent.com/127150137/236332353-921ef586-379a-49c6-8d5f-acac12d98304.jpg)

The purpose of this report is to help retailers increase sales by predicting food items sold at various stores and better understand what affects the sales.

## **Data Source:**
https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/
## **Data Link:**
[sales_predictions_2023.csv](https://github.com/Mhoover41/Prediction-of-Product-Sales/files/11401628/sales_predictions_2023.csv)

## **Data Dictionary**

![Data Dictionary](https://user-images.githubusercontent.com/127150137/236072592-f1a358bd-42af-4489-945b-95c302f61c96.png)
# **Exploratory Data Analysis**:
- During the exploratory data analysis, a boxplot and histogram was visualized for each numeric datatype column. 
- A barplot was visualized for each categorical column. 
- This gave a good baseline for all of the numeric and categorical columns for univariate EDA. 

![Fat bar plot](https://user-images.githubusercontent.com/127150137/236330360-859ccc7a-1b3c-4b01-a3a7-0aeeb5bab1bb.png)


This bar plot shows the distribution of Low Fat items versus Regular.

# **Explanatory Data Analysis**:

## **Key Questions:**

1) **How does Item MRP affect Item Outlet Sales?**
   
   There is a positive correlation between Item Outlet Sales and Item MRP. As the list price or Item MRP increases, the Item Outlet Sales increases.

![#1 Item outlet Sales vs Item MRP](https://user-images.githubusercontent.com/127150137/236072799-e46ae938-3483-4127-a818-2902b6474aa6.png)

2) **Is there a correlation between Item Outlet Sales and Item Weight?**
    
    No, there is no correlation as the regression line is flat. 
   
   ![#2 Item Outlet Sales vs Item Weight](https://user-images.githubusercontent.com/127150137/236072904-434c6e15-8be8-4208-9885-ce50a5295d87.png)
   
3) **Which Item type has the most sales?** 
   
   Fruits and Vegetables has the highest sales with Seafood having the lowest sales. Fruits and Vegetables accounted for 15% of sales, Snack Foods 14%, and Household        Items 11%. 
   
   ![#3 Total Sales by Item Type](https://user-images.githubusercontent.com/127150137/236072911-3bd51acb-4baf-4fed-8ea1-4436192899d6.png)

4) **Which outlet size had the most sales?**
   
   Medium outlet size had the most item outlet sales at 40% however we also had 23% of values that are unknown.
   
   ![#4 Item Outlet Sales by Outlet Size](https://user-images.githubusercontent.com/127150137/236072848-3d53475e-dc28-47c3-a243-15d337b22f5e.png)

5) **Which Item Fat Content had the highest sales?**  
   
   Low Fat items sold the most at nearly ₹ 12,000,000 in total sales which was 64% of total sales. 
   
   ![#5 Item Outlet Sales by Item Fat Content](https://user-images.githubusercontent.com/127150137/236072860-c6c56209-996a-4508-ae91-09fde188cfd0.png)
   
6) **Does item visibility affect sales?**
   
   There is no correlation between item outlet sales and item visibility.
   
   ![#6 Item Outlet Sales vs Item Visibility scatter plot](https://user-images.githubusercontent.com/127150137/236072862-7b5843cf-c74c-44ec-b69c-827d1d7ac86b.png)
   
7) **Does Outlet Location Type affect Sales?**
   
   Yes, Tier 3 Outlet Location Type contributed the most sales with 41%.
   
   ![#7 Total Sales by Outlet Location Type](https://user-images.githubusercontent.com/127150137/236072869-b5da30f1-0650-4716-b993-f2c0d3b6554f.png)
  
## **Key Insights:**
  - Customers are buying more Low Fat foods than Regular
  - Tier 3 Location Outlet Type contributed the most to sales
  - Vegetables and Fruits had the highest sales with Snack foods being a close second

## **Machine Learning Using the Following Models:**
- Linear Regression Model
- Decision Tree Regressor Model

## **Models Evaluated & Results:**

- Linear Regression Model (Testing Set):
  - MAE: 803.9572
  - MSE: 1,194,317.0807
  - RMSE: 1,092.8482
  - R2: 0.5671

- Tuned Decision Tree Regressor Model (Testing Set):
  - MAE: 738.3556
  - MSE: 1,118,187.9463
  - RMSE: 1,057.4441
  - R2: 0.5947

## **Recommendations:**
   
### Model Recommended: Decision Tree

   - Decision Tree had the lowest MAE of 738.36. This means our model was off on it's predictions by ₹738.36.

   - The mean Item Outlet Sales was ₹2181.39 which translates to an error percentage of 33.85%.

   - We have a lower error percentage on Decision Tree vs Linear Regression.

   - The Root Mean Squared Error is also lower for the Decision Tree, meaning that there are less outliers throwing off the weight of our model.

   - The R2 score is higher/better on the Decision Tree Model and this model uses 59.47% of the variance of the data.

## Project Revisited
**Linear Regression Model:**
Interpreting Our Model's Coefficients
   - Intercept: Our model assumed a baseline Item Outlet Sales of -₹137.99
   - Outlet_Type_Grocery Store:
      - If the item sold belongs to this category, the Item_Outlet_Sales will be decreased by ₹1590.41.
   - Outlet_Type_Supermarket Type 3:
      - If the item sold belongs to this category, the Item Outlet Sales increases by ₹1500.88
   - Outlet_Type_Supermarket Type 1: 
      - If the item sold belongs to this category, the Item Outlet Sales increases Item Outlet Sales by ₹275.17

![linear_regression_top3_coefficients](https://github.com/Mhoover41/Prediction-of-Product-Sales/assets/127150137/1b00fe25-cad9-4bd2-85cc-53ea14b59c1e)

- Random Forest Model:  Feature Importances Plot
  
![default_random_forest_top5_important_features](https://github.com/Mhoover41/Prediction-of-Product-Sales/assets/127150137/6103304e-197d-40d0-8d9f-48328774fed4)
