# Hotel-Booking-Cancel-Prediciton 
Predict potential cancel booking customers to accuracy up demand forecast

# Project Overview
- Build model to predict potential cancel booking customers
- Dataset is obtained from [Hotel_Booking] (https://www.kaggle.com/mojtaba142/hotel-booking)
- Handled missing values in columns `children`  which is caused because the customer did not fill in the number of children they brought, so we handle it by assuming that they do not bring children at all, `country` if we fill it with mode, it is feared that our model will increase so that it will be dropped, `agent` about 13.6% of the data is nan, so we can handle it by dropping and `company` reaches 94% is nan, so we need to drop and invalid values in column `adr` handle it by dropping
- Drop the features that can't be used for the model namely `reservation_status`, `name`, `email`, `phone number`, `credit_card`, and `reservation_status_date`
- Handle outliers with z- score and standardization/ normalization
- Column `country`, `last_name`, and `prefix_phone_number` is handled by feature hasher (many unique value) . Columns with categorical values is handled with one-hot encoding
- Train model with 5 different algorithms
- Validate the model with data test
