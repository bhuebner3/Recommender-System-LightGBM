
# H&M Personalized Fashion Recommendations Using XGBoost

## Project Overview
This project explores the development of a recommender system for the fashion industry, specifically tailored for H&M's extensive product catalog. With the surge in online shopping, providing personalized recommendations has become crucial for enhancing customer experience and driving sales. Given the dynamic nature of fashion trends and the challenge of limited explicit feedback, this project adopts XGBoost, a non-traditional machine learning algorithm, to offer personalized fashion recommendations.

## Motivation
The fashion industry's fast-paced environment and the vast selection of products present significant challenges for developing effective recommender systems. Traditional methods often struggle with the lack of explicit ratings and high return rates. This project aims to leverage transaction, customer, and product metadata to build a model that can navigate these challenges and improve the shopping experience by providing relevant product recommendations.

## Data
The dataset provided by H&M for the Kaggle competition (https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations) comprises two years of customer transaction data, including 1.3M unique customers and over 100K fashion items, resulting in 32M transactions. The data encompasses previous transactions, customer demographics, product metadata, text from product descriptions, and images of the garments.

## Methodology
### Feature Engineering
A significant portion of this project focused on feature engineering, extracting valuable insights from text data using Term Frequency-Inverse Document Frequency (TFIDF) and creating features based on purchase history and item attributes. 

### Models Evaluated
1. **Popular Items (Baseline)**: Recommending the 12 most popular items to all customers served as the baseline for comparison.
2. **User-User Collaborative Filtering (UUCF)**: A memory-based collaborative filtering approach focusing on user-item interactions.
3. **Light Gradient Boosting Machine (LGBM)**: A model-based approach utilizing gradient boosting techniques for binary classification tasks, ultimately selected for its performance and computational efficiency.

## Results
The evaluation metric used was Mean Average Precision @ 12 (MAP@12), with the LGBM model significantly outperforming the baseline and UUCF approaches. The project demonstrates the effectiveness of using gradient boosting and feature engineering to tackle the challenges inherent in fashion recommender systems.

## Discussion
The analysis highlighted the potential of non-traditional algorithms in building effective recommender systems for the fashion industry. Future improvements could focus on refining the item retrieval process and exploring methods to address the cold start problem. Additionally, considering business implications and customer satisfaction metrics beyond the competition's evaluation criteria could provide more holistic insights into the recommendations' effectiveness.

## Conclusion
This project underscores the value of advanced machine learning techniques in developing recommender systems for the fashion industry. By adopting a methodical approach to feature engineering and leveraging the power of XGBoost, we can offer personalized recommendations that enhance the shopping experience, drive sales, and potentially reduce the environmental impact through minimized returns.


**File Descriptions:**

Article_EDA - Exploratory data analysis of article file. Also creates combined plot of age and index

Baseline - Creates and evaluates baseline model

First_Attempt-Copy1 - Not relevant. Scratch code for subsetting data ect

LGBM_article2vec - performs TFIDF and item cos similarity

LGBM_model_train - implements and evaluates model

Subsampling - Creates train and test sets

Transactions_EDA - Exploratory data analysis of customers file + transactions file

UUCF - Implement and evaluate UUCF model
