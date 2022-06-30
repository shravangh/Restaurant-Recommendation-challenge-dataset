# Restaurant-Recommendation-system

The dataset is obtained from datasets of kaggle https://www.kaggle.com/datasets/mrmorj/restaurant-recommendation-challenge. The train dataset
consists of customer and vendor information like location, previous orders, order_tags, vendor_menu_tags, time of opening of restaurant etc.
The target column in train dataset is whether the customer ordered from the vendor or not i.e 1/0. The challenge is to predict given a different
combinations of customer, vendor and location whether a customer would order or not.

Based on initial EDA done on the train dataset, a list of columns are deemed important and pre-processing is done on those variables.

1. Categorical variables are one-hot encoded.
2. Numerical features are normalised.
3. A new variable is created called 'previous orders' based on orders made by customer by the same vendor.
4. BOW representation is applied on vendor_tag_name as it consists of text data.
5. Similarity among customers and vendors is calculated by creating a matrix across customers and vendors and for every customer top 5 similar customers
are taken as features and also for every vendor top 5 similar vendors are taken as features.
6. All features are concatenated.
7. Since the data is imbalanced the minority class is upsampled and various ML models are applied to predict the output on test dataset.
8. Further the SurPRISE models are used to create more features with the number of orders feature as target variable.
9. The output of SurPRISE models are made the new features and are added to previous features. The model is trained on this dataset.
10. F1 score is chosen as performance metric and performance of various models is displayed in the notebook.
