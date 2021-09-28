# Hotel-Booking-Cancel-Prediciton 
Predict potential cancel booking customers to accuracy up demand forecast

# Project Overview
- Build model to predict potential cancel booking customers
- Dataset is obtained from [Hotel_Booking] (https://www.kaggle.com/mojtaba142/hotel-booking)
- Handled missing values and invalid values 
- Handle outliers 
- Feature encoding
- Train model with 5 different algorithms


## Problem
Lose potential of sales due to cancel booking customer, while tourism market is growing each year

## Goals
Increase revenue from primary business (room sales)

# Early Insight from The Data
1. Booking cancellation rate problem up to 37%
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/booking_cancellation_rate.png)
2. Customers with transient types have the biggest cancellation rate compared to other types of customers
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/customer_type.jpg)
3. Customers with Non-Refund deposit types have the biggest cancellation rate compared to other types of deposit type
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/deposit_type_2.jpg)
4. The lowest cancellation rate is from November to March (Autumn - Winter) and the highest is April to October (Spring - Summer).
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/Cancellation_rate_month.jpg)

## Data Cleansing and Preprocessing
- Handled missing values in columns `children`  which is caused because the customer did not fill in the number of children they brought, so we handle it by assuming that they do not bring children at all, `country` if we fill it with mode, it is feared that our model will increase so that it will be dropped, `agent` about 13.6% of the data is nan, so we can handle it by dropping and `company` reaches 94% is nan, so we need to drop and invalid values in column `adr` handle it by dropping
- Drop the features that can't be used for the model namely `reservation_status`, `name`, `email`, `phone number`, `credit_card`, and `reservation_status_date`
- Handle outliers with z- score and standardization/ normalization
- Column `country`, `last_name`, and `prefix_phone_number` is handled by feature hasher (many unique value) . Columns with categorical values is handled with one-hot encoding

## Model Building
I tried four different Scenarios to apply to the model. First, split the data into train set & test set (size is 30%). Trained the model with 5 different algorithms and evaluated them with Precision. Precision metric used to minimize in correctly prediciting customer who are not going to cancel booking as cancel. The model was trained with:

- Logistic Regression
- Decission Tree
- Adaboost
- Random Forest
- XGboost

## Model Evaluation
The Random Forest model far outperformed the other approaches. The model were evaluated with Precision

| Eval Metrics / Classifier | Logistic Regression | Decission Tree | Adaboost | Random Forest | XGboost |
| :---                      |    :----:           |    :---:       | :---:    | :---:         | :---:   |
| Accuracy                  | 0.81                | 0.85           | 0.83     | 0.89          | 0.81    |
| Precision                 | 0.79                | 0.81           | 0.82     | 0.89          | 0.86    |
| Recall                    | 0.70                | 0.82           | 0.71     | 0.81          | 0.81    |
| F1-score                  | 0.74                | 0.81           | 0.76     | 0.85          | 0.83    |
| AUC                       | 0.79                | 0.85           | 0.81     | 0.87          | 0.86    |

# Business Recomendations
### Cancellation Policies
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/BusinessRecom1.png)
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/BusinessRecom2.png)
### Overbooking Strategy
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/BusinessRecom3.png)
### Revenue Simulation
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/BusinessRecom4.png)
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/BusinessRecom5.png)
### Project Evaluation
![](https://github.com/muhfadilf/Hotel-Booking-Cancel-Prediciton/blob/main/images/BusinessRecom6.png)
