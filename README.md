# Customer-Churn_Prediction

# Summary
The cost of getting new customers is higher than retaining existing ones. ABC bank seeks to prevent customer churn by having to identify customers at risk of leaving and try implement strategies to retain them. The project aims compare the performance of Random Forest and LightGBM models in predicting customer churn, and providing LIME explanations for their predictions.

The data is from [Kaggle](https://www.kaggle.com/datasets/shubhammeshram579/bank-customer-churn-prediction). In this study, using Python we aim to;
1. Identify factors that affect customer churn.
2. Compare how the two prediction models perform in classifying whether a customer exits or not.
3. Use LIME to explain the predictions of the models.

# Data overview.
- The dataset contains 10000 observations and 14 feaures.
- The dataset has no missing values.
- We have seven variables are categorical while 6 are numerical.
- We drop 3 insignificant features (rownumber, customerid and surname)and remain with 11 features.

 # Exploratory Data Analysis.
 - The proportion of customers exited is 20% of the data while those retained was around 80%. 
  ![image](https://github.com/user-attachments/assets/9749a45b-f65b-4edd-871d-b0623f3a2986)
 - According to our data, majority of the customers are from France and in terms of sex,most of the customers are female.
- Features towards customer churn:
   - More females exited than males.
   - Higher credit scorers less exited than lower credit scorers.
   - Surprisingly, most of the customers who exited are those who had credit 
     cards than those who didn't have. However, majority of the customers in 
     the dataset have credit cards.
   - Younger people exited more than older people. This means the bank needs 
     to strategize how to consider different age groups in their bank.
   - Most exitors had less years with the bank.
   - Active members exited less than non active members. The bank might 
     implement something that may activate the non active customers.
   - Customers with higher bank balances exited less than those with lower 
      balances.  
   - Those with higher estimated salaries exited less than those with lower 
      salaries.
   - We do not have more information on the bank products bought by a 
     customer. We see that all those who had most products exited. It seems like the number of products a customer has with the bank is not as important as the product itself. 
- Age is weakly positive correlated to the churn of customers and balance is weakly negative correlated to number of products. This means the higher the bank balance the less the number of products a customer has.
  # Modelling.
- Before building the models;
  - We encoded the categorical variables before building the models.
  - We split the data into two; 80% for model training and 20% for testing.
  - Using recursive feature selection with cross validation method, HasCreditCard feature is not significant in predicting customer churn. We dropped the feature.
  - Features like credit score and estimated salary have high standard 
  deviations, therefore standardization is necessary to ensure the data is on the same scale to avoid misleading results.
  - Our y variable is not balanced, we use smote to balance the ratio of the classes to avoid misleading results.
- We then build our models on balanced and imbalanced dataset to check how the models perform.

  # Results
- Using accuracy to evaluate how the models performing.
- The accuracy of both models reduce after data is balanced. This means that accuracy is not a good metric to consider when data is imbalanced.
- Random forest has an accuracy of 83% while LightGBM classifier 82%. 
- Lime helps us see how the prediction of a model comes to be.
- It also show us that when the data is not balanced, the model tends to favour the majority class. This leads to misleading results.

  # Conclusion
- Both models can be used to predict customer churn.
- Imbalanced data sets lead to misleading results. The model may lead to the majority class.
- Use of LIME provides more transparency on the model's prediction.
