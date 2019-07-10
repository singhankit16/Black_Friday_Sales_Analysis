 
=======
# Black Friday Sales Analysis

### Abstract 
We all eagerly wait for Black Friday sales and plan ahead in order to make most out of it. Similar is the objective of a retail outlet on Black Friday. They also aspire to bring the best out of this day.  The major objective of a store is to maximize the revenue on this day, by selling off a large proportion of their unsold inventory. The main challenge to achieve this objective is “What optimal prices should the store set to capture demand that maximizes revenue?” The problem we solve would help the business to get the predicted Purchase amount (or Willingness to Pay) for each product for each user. They can use this then to set optimal prices on the product (using Multinomial Model for Price Optimization or others). So, when we find Black Friday Sales Analysis data on Kaggle, it highly motivated our team to work for this interesting real-world problem for ABC Retail Store.

### Exploratory Data Analysis
Dimensions of dataset: 
Rows: 550K 
Columns:  12 
Due to resource constraints we took a subset of 150K observation for our analysis. 
We further split the data into Train and Test data with 70:30 
Train Dataset: 104981 rows * 16 columns 
Test Dataset: 45019 rows * 16 columns 

### Data Description 
Data Description The dataset consists of 12 features [Table 1] 

The dataset consists of 12 features [Table 1]

                                                      #### Features and Description 
                                            Features                  Description 
                                            User_ID                   Customer ID unique to each customer 
                                            Product_ID                Product ID assigned to each unique product 
                                            Gender                    Customer Gender 
                                            Age                       Range of age of the customer 
                                            Occupation                Occupations of Customer from 1-20 
                                            City_Category             Category of City from A to C 
                                            Current_City_Years        Duration of Stay in Current City 
                                            Marital_Status            Marital Status of Customer 
                                            Product_Category_1        Product Category 1 of products from 1-18 
                                            Product_Category_2        Product Category 2 of products from 2-18 
                                            Product_Category_3        Product Category 3 of products from 3-18 
                                            Purchase                  Purchase amount (Target Variable) 
 
 ### Feature Engineering

Customer and Product Id are two important categorical features in the dataset. But due to the high cardinality of 5k and 3k Levels, 
including those two features in the model lead to great computation resources and time. While ignoring the two features the model is performing poorly. So, we included the count of customer id for each unique customer id. This helps us to explain the number of purchases the user has made which is can help explain some properties of the user. We also used Median, Quartile 1 and Quartile 3 values of purchase amount corresponding to each product id. We thought that if a product may be sold to different users for different amounts, the distribution of how high, low or the median amount paid for that product help us predict the purchase amount better. This step helped our models greatly in accounting the variability and increase accuracy on predicted purchase amounts.

### Experimental Results
 
 ![image](https://github.com/singhankit16/Black_Friday_Sales_Analysis/blob/master/Model_results.PNG)
 

### Conclusion

Concluding, we learned a great deal about the dataset that we were given for this competition and the subset of the test data which we decided to use for the project. We had a few questions at the start of this project, of which the most important was: “If none of the powerful models are working, what changes should we do to lower down our RMSE”. The answer to this question was “Feature Engineering”, the most important and distinguishing factor. We learned to leverage the art of feature engineering and how it can make all the difference in the performance of the model. The next hindrance we faced was computation on such a huge dataset using standard configuration machines. Apache’s H2O package was the real savior and helped to increase our efficiency by lowering down the model computation time. In terms of model evaluation, we did use a fair evaluation strategy using cross-validation for regularization hyperparameters and GLM was selected to be the winner. GLM captured the variance between training and test dataset by maintaining good bias-variance trade-off and giving high performance on RMSE metric. Overall, while doing this project, effectively implementing advanced analytics practices, we learnt about the importance of memory optimization, understanding the dataset thoroughly and feature engineering. The message for us was that in the real world the model optimization and evaluation can only be done once all these steps have been thoroughly worked on before.

### Reference

- https://en.wikipedia.org/wiki/Generalized_linear_model 
- Hastie T, Tibshirani R, Friedman J. The Elements of Statistical Learning [Internet]. New York, NY: Springer New York; 2009. Available: http://link.springer.com/10.1007/978-0-387-84858-7 
- https://www.kdnuggets.com/2017/10/xgboost-top-machine-learning-method-kaggle-explained.html 
- Rennie JD, Shih L, Teevan J, Karger D. Tackling the poor assumptions of naive bayes text classifiers. International Conference on Machine Learning. 2003. p. 616. Available: http://www.aaai.org/Papers/ ICML/2003/ICML03-081.pdf 
- Analytics Vidhya Discussion Forum - https://discuss.analyticsvidhya.com/t/black-friday-data-hack-reveal-your-approach/ 5986/8  
- Understanding feature engineering in R - https://blogs.msdn.microsoft.com/microsoftrservertigerteam/2017/03/23/feature -engineering-using-r/ 
- Diving into H2o - https://www.r-bloggers.com/diving-into-h2o/ 
- H2o package reference in R - https://www.rdocumentation.org/packages/h2o/versions/3.20.0.8

