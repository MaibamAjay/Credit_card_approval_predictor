# Introduction
### Predicting a good credit card client is immensely valuable for a bank for several reasons
1.Risk Mitigation: Identifying clients who are likely to be responsible borrowers reduces the risk of defaults and late payments. This, in turn, helps the bank preserve its assets and maintain a healthy loan portfolio.

2.Profitability: Good credit card clients tend to use their cards regularly and pay their bills on time. This generates interest income for the bank in the form of finance charges. Additionally, responsible clients are more likely to use other banking services, such as loans and mortgages, which further boosts the bank's profitability.

3.Reduced Operational Costs: Clients with a history of responsible credit card usage typically require less customer service and dispute resolution, resulting in lower operational costs for the bank.

4.Customer Retention: By providing credit cards to clients who can manage them responsibly, the bank enhances customer satisfaction and loyalty. Satisfied clients are more likely to stay with the bank for other financial products and services.

5.Compliance and Regulatory Requirements: Many regulatory bodies require financial institutions to assess credit risk accurately and responsibly. Predicting good credit card clients helps the bank comply with these regulations and maintain a good reputation.

6.Competitive Advantage: Banks that can efficiently assess credit risk and attract low-risk clients gain a competitive edge in the industry. They can offer better terms and lower interest rates to attract quality clients.

7.Improved Asset Quality: A portfolio of credit cards held by good clients is considered a valuable asset for the bank, enhancing its overall asset quality and creditworthiness.

8.Data for Business Intelligence: Accurate credit risk assessment generates valuable data on client behavior and financial habits. This data can be used for market research, product development, and targeted marketing efforts.

9.Enhanced Capital Allocation: Knowing which clients are likely to be good credit card customers allows the bank to allocate capital more efficiently and reduce provisions for loan losses.

10.Risk Diversification: A bank with a mix of high and low-risk clients can diversify its risk, reducing exposure to economic downturns and unforeseen events

 
# Project problem statement
The bank has been using credit score measure to check the eligibility of the customers for issuing the credit card. Now, in addition to the credit score, the bank want to include the personal informations of their customers in deciding the credit card eligibility.


# Objective
1. To determine which personal informations(features) are more helpful in predicting the credit card eligibilty.
2. Since the WRONG Credit Card Approval(False Positive) is very costly for the bank, the most important evaluation metrics of this Classification model should be Precision Score. 
So, The Classification model having the highest Precision Score is to be chosen.
 
# Description of the dataset

1. The dataset contains 1548 rows and 18 columns. The target dataset(Credit_card_label.csv) is provided separately.

2. It has 8 categorical features and 10 numerical features.

3. It is an unbalanced dataset(10% Minority, 90 % Majority).

4. The following list describes each of the dataset's features:


Features name: (Credit_Card.csv)

​
Ind_ID: Client ID

​
Gender: Gender information

​
Car_owner: Having car or not

​
Propert_owner: Having property or not

​
Children: Count of children

​
Annual_income: Annual income

​
Type_Income: Income type

​
Education: Education level

​
Marital_status: Marital_status

​
Housing_type: Living style

​
Birthday_count: Use backward count from current day (0), -1 means yesterday.

​
Employed_days: Start date of employment. Use backward count from current day (0). Positive value means, individual is currently unemployed.

​
Mobile_phone: Any mobile phone

​
Work_phone: Any work phone

​
Phone: Any phone number

​
EMAIL_ID: Any email ID

​
Type_Occupation: Occupation

​
Family_Members: Family size

​
​
Another data set (Credit_card_label.csv) contains two key pieces of information
​
ID: The joining key between application data and credit status data, same is Ind_ID
​
Label: 0 is application approved and 1 is application rejected. 


# Challenges and solutions approaches while using this dataset
1. The small dataset size is a problem for training machine learning model since such dataset has 
​
    -the potential of overfitting(low bias, high variance)
    
    -insufficient data to properly train all the independent features which will results in improper ml model
    
    
    APPROACHES:
        
    -Since the dataset is very small, the Number of Independent Features to be used for model building should be as fewer as possible.
    
    -the number of categories for each categorical features should be made as fewer as possible since the dataset is very small
    
    -Since there is a high chance of overfitting with this small dataset, simple machine learning algorithms like logistic regression is prefered first, and ensemble methods like random forest or boosting technique like xgboost are also used.
    Naive Bayes algorithm also works well in small and complex datasets. So, it is also included in the list.
    
​
2. The dataset is unbalanced and it will create a bias model if an algorithm is trained using this raw dataset.
    
    APPROACHES:
    2 possible approaches arises while dealing with unbalanced dataset

    
    - To select the significance features first and handle the unbalanced data(oversampling in this case)

        
    - To handle the unbalanced data first and select the significance features later.

      
    -According to a study, for a highly unbalanced dataset, it is better to do the feature selection first and then handle the unbalaced data later rather than handling the imbalanced data first and then do the feature selection. The link of the study is attached below
    
    https://www.mdpi.com/2076-3417/11/14/6574#:~:text=Note%20that%20IG%2BSMOTE%20and,represent%20the%20opposite%20combination%20order.

​
​
    -The unbalanced dataset is handled using imbalanced-learn library

    
    -Since the dataset is very small, oversampling methods is used.

​
# Techniques and tools used in building the model
​
1. Sklearn and imblearn pipelines are used to streamline the transformations for both the training and testing dataset.
​
2. Custom transformers are created and used in the pipelines to ease the transformation of the datasets.
​