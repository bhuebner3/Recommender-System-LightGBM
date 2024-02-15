
# H&M Personalized Fashion Recommendations Using XGBoost

## Project Overview
This project explores the development of a recommender system for the fashion industry, specifically tailored for H&M's extensive product catalog. With the surge in online shopping, providing personalized recommendations has become crucial for enhancing customer experience and driving sales. Given the dynamic nature of fashion trends and the challenge of limited explicit feedback, this project adopts XGBoost, a non-traditional machine learning algorithm, to offer personalized fashion recommendations.

## Objective
The primary objective of this project is to develop a robust recommender system using lightgbm. By leveraging a dataset comprised of customer transactions, product metadata, and additional content features, the project aims to:
- Improve the accuracy of fashion item recommendations for H&M's diverse customer base.
- Address the challenges posed by sparse explicit feedback through the innovative use of transactional and behavioral data.
- Utilize non-traditional machine learning techniques, specifically lightgbm, to explore new avenues in recommender system development within the retail sector.

## Data
The dataset provided by H&M for the Kaggle competition (https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations) comprises two years of customer transaction data, including 1.3M unique customers and over 100K fashion items, resulting in 32M transactions. The data encompasses previous transactions, customer demographics, product metadata, text from product descriptions, and images of the garments.

## Methodology
### Exploratory Data Analysis
The project begins with a thorough EDA, examining variable distributions and exploring the data to gain insights that may be used in feature engineering. Below is the plot showing customer age distribution, and most common items sold.

![eda](https://github.com/bhuebner3/H-M-Kaggle/assets/73898316/a5971c79-8822-45c8-a77a-e88678ed9e07)


### Feature Engineering
A significant portion of this project focused on feature engineering, extracting valuable insights from text data using Term Frequency-Inverse Document Frequency (TFIDF) and creating features based on purchase history and item attributes. 
Feautres include:
1. Text description extraction: TFIDF based on 2-grams
2. TFIDF score and item attributes used to create cosine
similarity between items and recently purchased items
3. Purchase history attributes created (item rebuy rate, number
of purchases in the same category, section, ect)

![word_cloud](https://github.com/bhuebner3/H-M-Kaggle/assets/73898316/ff1906ab-e29a-493b-a4f2-555914d871c7)


### Models Evaluated
1. **Popular Items (Baseline)**: Recommending the 12 most popular items to all customers served as the baseline for comparison.
2. **User-User Collaborative Filtering (UUCF)**: A memory-based collaborative filtering approach focusing on user-item interactions.
3. **Light Gradient Boosting Machine (LGBM)**: A model-based approach utilizing gradient boosting techniques for binary classification tasks, ultimately selected for its performance and computational efficiency.

![gbm_small](https://github.com/bhuebner3/H-M-Kaggle/assets/73898316/9d8142c4-b097-41e4-8fd7-ed124689fc1d)





## Results
The evaluation metric used was Mean Average Precision @ 12 (MAP@12), with the LGBM model significantly outperforming the baseline and UUCF approaches. The project demonstrates the effectiveness of using gradient boosting and feature engineering to tackle the challenges inherent in fashion recommender systems.

![results](https://github.com/bhuebner3/H-M-Kaggle/assets/73898316/89fa1ee1-323a-4690-a9db-e93f3448380a)



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
