
ABSTRACT 

We all eagerly wait for Black Friday sales and plan ahead in order to make most out of it. Similar is the objective of a retail outlet on Black Friday. They also aspire to bring the best out of this day.  The major objective of a store is to maximize the revenue on this day, by selling off a large proportion of their unsold inventory. The main challenge to achieve this objective is “What optimal prices should the store set to capture demand that maximizes revenue?” The problem we solve would help the business to get the predicted Purchase amount (or Willingness to Pay) for each product for each user. They can use this then to set optimal prices on the product (using Multinomial Model for Price Optimization or others). So, when we find Black Friday Sales Analysis data on Kaggle, it highly motivated our team to work for this interesting real-world problem for ABC Retail Store. 
 
 
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
 
 ![image] (https://github.com/singhankit16/Black_Friday_Sales_Analysis/blob/master/Model_results.PNG)

