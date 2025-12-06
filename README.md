# Sentiment Analysis of SXSW 2011 Tweets - README

## Project Overview

This project performs sentiment analysis on tweets from the SXSW 2011 conference to analyze customer opinions about technology brands and products. The goal is to help businesses understand customer perception, prioritize product improvements, and measure satisfaction by automatically classifying tweets as positive, negative, or neutral.

## Business Problem
Businesses struggle to:

* Determine customer sentiment from unstructured social media data.

* Prioritize product improvements based on customer feedback.

* Predict customer churn and measure satisfaction.

* Identify what customers value vs. what needs improvement.

## Solution
A machine learning pipeline that:

* Processes and cleans tweet data.

* Classifies sentiment using multiple ML algorithms.

* Analyzes brand-specific sentiment patterns.

* Provides actionable business insights for product development.

## Dataset
* Source: SXSW 2011 conference tweets.

* Size: 9,093 tweets after cleaning.

* Features:

1. tweet_text: Original tweet content.

2. emotion_in_tweet_is_directed_at: Brand/product mentioned.

3. is_there_an_emotion_directed_at_a_brand_or_product: Sentiment label.

* Sentiment Distribution (original):

Positive: 33%

Neutral: 60%

Negative: 7%

### Key Challenges & Solutions
#### 1. Class Imbalance

![Distribution of sentiment lables (%)](https://github.com/Joan-omanyo/dsc-phase-4-project-v3-group-6/blob/main/images/Distribution%20of%20sentiment%20lables.png)

Problem: Severe imbalance (Neutral: 60%, Negative: 7%)

Solution: Applied SMOTE (Synthetic Minority Oversampling) to balance all classes to 5,388 instances each

#### 2. Text Preprocessing

Removed URLs, mentions, hashtags, and special characters.

Applied lemmatization and stopword removal.

Used TF-IDF with n-grams (unigrams + bigrams).

#### 3. Feature Selection

Used Chi-squared test for feature selection.

Optimal: 2,000 features provided best F1-score (0.6444).

##### Model Performance

Model Rankings (Accuracy)

* Random Forest: 69.1% (F1: 66.8%)

* Voting Classifier: 65.5% (F1: 64.5%)

* SVM: 64.6% (F1: 60.5%)

* Logistic Regression: 64.1% (F1: 61.8%)

* Multinomial NB: 63.2% (F1: 62.6%)

* Baseline (Naive Bayes): 64.8% (F1: 64.8%)

###### Best Model

Algorithm: Random Forest

Accuracy: 69.1%

Improvement over baseline: 6.5%

#### Brand-Specific Insights
![Top 10 most mentioned brands](https://github.com/Joan-omanyo/dsc-phase-4-project-v3-group-6/blob/main/images/Top%2010%20most%20mentioned%20brands.png)

Top Performing Brands (Highest Positive %)

iPad or iPhone App: 60.6% positive

Apple: 43.3% positive

iPad: 40.0% positive

Brands Needing Attention (Highest Negative %)
Google: 7.1% negative

iPhone: 5.0% negative

iPad or iPhone App: 4.3% negative

### Key Business Recommendations
1. Leverage Strengths
Focus on App Ecosystem: iPad/iPhone apps show highest positive sentiment (60.6%).

Amplify Apple's Success: Apple brand maintains strong positive perception.

Capitalize on Emotional Engagement: Apps generate the most emotional response.

2. Address Weaknesses
Investigate Google's Perception: Highest negative sentiment (7.1%) requires attention.

Diagnose iPhone Pain Points: Despite overall positivity, 5% negative sentiment indicates specific issues.

Monitor App Quality: Even top-performing apps have 4.3% negative feedback.

3. Strategic Actions
Product Development: Use negative feedback for targeted improvements.

Marketing Strategy: Highlight strengths in app ecosystem.

Competitive Analysis: Monitor sentiment trends across brands.

Continuous Monitoring: Establish ongoing sentiment tracking.

Pipeline Components

* Data Loading & Cleaning

* Text Preprocessing

* Feature Engineering (TF-IDF)

* Class Balancing (SMOTE)

* Model Training & Evaluation

* Hyperparameter Tuning

* Ensemble Methods

#### Future Improvements
* Technical Enhancements
Transformer Models: Implement BERT or RoBERTa for better context understanding.

Advanced Balancing: Try different oversampling/undersampling techniques.

Feature Engineering: Incorporate sentiment lexicons and emotion scores.

Real-time Analysis: Build streaming pipeline for live tweet analysis.

* Business Applications
Dashboard Development: Create real-time sentiment monitoring dashboard.

Competitive Intelligence: Expand to multiple social media platforms.

Trend Analysis: Track sentiment changes over time.

Alert System: Set up notifications for negative sentiment spikes.

### Conclusion
This project successfully:

1. Built a functional sentiment analysis model with 69.1% accuracy.

2. Identified key brand sentiment patterns.

3. Provided actionable business recommendations.

4. Established a repeatable feedback loop for product improvement.

5. Delivered a deployable model with clear performance metrics.

The model serves as a foundation for automated customer feedback analysis, enabling data-driven decision making for product development and marketing strategy.
