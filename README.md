
# H&M Personalized Fashion Recommendations Using LightGBM

## Project Overview
This project explores the development of a recommender system for the fashion industry, specifically tailored for H&M's extensive product catalog. With the surge in online shopping, providing personalized recommendations has become crucial for enhancing customer experience and driving sales. Given the dynamic nature of fashion trends and the challenge of limited explicit feedback, this project adopts XGBoost, a non-traditional machine learning algorithm, to offer personalized fashion recommendations.

## Objective
The primary objective of this project is to develop a robust recommender system using LightGBM. By leveraging a dataset comprised of customer transactions, product metadata, and additional content features, the project aims to:
- Improve the accuracy of fashion item recommendations for H&M's diverse customer base.
- Address the challenges posed by sparse explicit feedback through the innovative use of transactional and behavioral data.
- Utilize non-traditional machine learning techniques, specifically LightGBM, to explore new avenues in recommender system development within the retail sector.

## Tools and Libraries Used
- **Pandas & Numpy**: For data manipulation and numerical operations.
- **Scikit-learn**: For model selection, preprocessing, and machine learning utilities.
- **LightGBM (LGBM)**: For implementing the gradient boosting model.
- **NLTK & WordCloud**: For text processing and generating word clouds from product descriptions.
- **Matplotlib**: For data visualization.
- **Scipy**: For sparse matrix operations and linear algebra.

## Techniques Used
- **Text Processing (NLP)**: Utilized Term Frequency-Inverse Document Frequency (TF-IDF) for extracting insights from product descriptions.
- **Truncated Singular Value Decomposition (SVD)**: Reduced the dimensionality of TF-IDF vectors to create compact representations of articles.
- **Nearest Neighbors**: Identified similar articles based on their vector representations to suggest items with similar characteristics.
- **Gradient Boosting with LightGBM**: Utilized for the core recommendation model, predicting customer preferences based on engineered features.
- **Feature Engineering**: Extensively engineered features from transactional data, customer demographics, and article attributes to capture diverse interactions and preferences.
- **Cosine Similarity**: Calculated similarity scores between articles to enhance recommendation relevance.
- **Collaborative Filtering**: Explored User-User Collaborative Filtering (UUCF) for recommendations based on similar user behaviors.


## Data
The dataset provided by H&M for the Kaggle competition (https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations) comprises two years of customer transaction data, including 1.3M unique customers and over 100K fashion items, resulting in 32M transactions. The data encompasses previous transactions, customer demographics, product metadata, text from product descriptions, and images of the garments.

## Methodology
### Exploratory Data Analysis
The project begins with a thorough EDA, examining variable distributions and exploring the data to gain insights that may be used in feature engineering. Below is the plot showing customer age distribution, and most common items sold.

![eda_small](https://github.com/bhuebner3/H-M-Kaggle/assets/73898316/954d9641-a92e-4f68-8417-00c5c930512d)



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

![results_small](https://github.com/bhuebner3/H-M-Kaggle/assets/73898316/13f98ced-74e4-4c3f-8c6e-4706bc5e28e3)




## Discussion
The analysis highlighted the potential of non-traditional algorithms in building effective recommender systems for the fashion industry. Future improvements could focus on refining the item retrieval process and exploring methods to address the cold start problem. Additionally, considering business implications and customer satisfaction metrics beyond the competition's evaluation criteria could provide more holistic insights into the recommendations' effectiveness.

## Conclusion
This project underscores the value of advanced machine learning techniques in developing recommender systems for the fashion industry. By adopting a methodical approach to feature engineering and leveraging the power of XGBoost, we can offer personalized recommendations that enhance the shopping experience, drive sales, and potentially reduce the environmental impact through minimized returns.

