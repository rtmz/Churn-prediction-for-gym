# Churn prediction for gym

In order to fight churn, the gym chain 'Model Fitness' has digitized a number of its customer profiles. Our task is to analyze them and come up with a customer retention strategy. For a gym, it makes sense to say a customer has left if they don't come for a month.

We'll:

- Learn to predict the probability of churn (for the upcoming month) for each customer
- Draw up typical user portraits: select the most outstanding groups and describe their main features
- Analyze the factors that impact churn most
- Draw basic conclusions and develop recommendations on how to improve customer service:
  - Identify target groups
  - Suggest measures to cut churn
  - Describe any other patterns you see with respect to interaction with customers
 
# Data description:

 CSV files containing data on churn for a given month and information on the month preceding it. The dataset includes the following fields:

- 'Churn' — the fact of churn for the month in question

Current dataset fields:

User data for the preceding month:
- 'gender'
- 'Near_Location' — whether the user lives or works in the neighborhood where the gym is located
- 'Partner' — whether the user is an employee of a partner company (the gym has partner companies whose employees get discounts; in those cases the gym stores information on customers' employers)
- Promo_friends — whether the user originally signed up through a "bring a friend" offer (they used a friend's promo code when paying for their first membership)
- 'Phone' — whether the user provided their phone number
- 'Age'
- 'Lifetime' — the time (in months) since the customer first came to the gym

Data from the log of visits and purchases and data on current membership status

- 'Contract_period' — 1 month, 3 months, 6 months, or 1 year
- 'Month_to_end_contract' — the months remaining until the contract expires
- 'Group_visits' — whether the user takes part in group sessions
- 'Avg_class_frequency_total' — average frequency of visits per week over the customer's lifetime
- 'Avg_class_frequency_current_month' — average frequency of visits per week over the preceding month
- 'Avg_additional_charges_total' — the total amount of money spent on other gym services: cafe, athletic goods, cosmetics, massages, etc.

# We'll go through the following steps:

- Exploratory data analysis (EDA)

  - Look at the dataset: does it contain any missing features? Study the mean values and standard deviation.
  - Look at the mean feature values in two groups: for those who left (churn) and for those who stayed.
  - Plot bar histograms and feature distributions for those who left (churn) and those who stayed.
  - Build a correlation matrix and display it.
- Build a model to predict user churn

  - Build a binary classification model for customers where the target feature is the user's leaving next month.

  - Divide the data into train and validation sets using the train_test_split() function.
  - Train the model on the train set with two methods:
    - logistic regression
    - random forest
  - Evaluate accuracy, precision, and recall for both models using the validation data. Use them to compare the models. Determine which model gave better results.
  
- Create user clusters

    - Set aside the column with data on churn and identify object (user) clusters:

    - Standardize the data.
    - Use the linkage() function to build a matrix of distances based on the standardized feature matrix and plot a dendrogram.
    - Train the clustering model with the K-means algorithm and predict customer clusters.
    - Look at the mean feature values for clusters.
    - Plot distributions of features for the clusters.
    - Calculate the churn rate for each cluster (use the groupby() method). Determine which clusters are prone to leaving, and which are loyal.
  
