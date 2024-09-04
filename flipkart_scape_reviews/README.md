# Flipkart Products Reviews Scraping with BeautifulSoup For Sentiment Analysis.

## Introduction

- The aim was to demonstrate the process we used to collect the data for flipkart product review sentiment analysis.
- The data is collected with a process of scraping product reviews from Flipkart using the BeautifulSoup library in Python.
- The main objective is to collect customer reviews and associated metadata from Flipkart for different products include electotronis, wears, household items etc.
- Data for these topics extracted are then used for a downstream task of labelling these reviews to either `positive, negative or neutral sentiments`.
- After Labelling the dataset, they will then parsed to a final process which involves training various models and compairing their perfomance on extracted dataset.

 
## Web Scraping
- Web scraping is the process involving sending request for a website contnent and then extracting data from the web pages download.
- The most common tools used include selenum, scapy and ofcourse beautiful soup to parse html content.
- This project uses **Beautiful Soup** for collection which is a Python library used for parsing HTML and XML documents.
- 

  
## Process Procedure
- The following is outline of how the data is scrapped.
1. **Requesting Desired Webpage:**
   - This involves sending request for the web content of a specific page on Flipkart product pages.
   - Since the site will block us due to too many requests, we will have a sleep time of about 5 seconds for each of the request to atleast prevent this.

2. **Extracting Data:**
   - Use beautiful soup to Parse the HTML for extraction.
   - The processed html conent will then help in easier extraction of review text, ratings, and other relevant information.


3. **Search-Based Product URL Discovery:**
   - To automate the process, we will have a request to search for a web page and then extract the urls from it for products. After this, we will extract atleast 10 product reviews for each product.

4. **Iterating Over Multiple Products and Pages:**
   - Iterate through multiple product pages and review pages to gather comprehensive data.

5. **Serializing the Dataframe to a CSV File:**
   - Use the extracted data and format them into a csv file for further process of the downstream task.


- Through above process, we will be able to scrape product reviews from Flipkart using BeautifulSoup, enabling further analysis and insights.

---
### Data Labelling
- To label data, we are going to use an analytical tool called VADAR (Valence Aware Dictionary and sEntiment Reasoner) for sentiment analysis on the reviews scraped from Flipkart.
- The tools allows us to get the scores for the  text and we can be able to determine its sentiment.
- To start, we need to clean the text  and then apply VADER's `SentimentIntensityAnalyzer` to classify each review as positive, negative, or neutral based on its sentiment polarity.
- The results contain `compound, neg, pos, neu` scores.
- The `compound score` is computed by summing the valence scores of each word in the lexicon, adjusted according to the rules, and then normalized to be between -1 (most extreme negative) and +1 (most extreme positive). This is the most useful metric if you want a single unidimensional measure of sentiment for a given sentence. Calling it a 'normalized, weighted composite score' is accurate.
- It is also useful for researchers who would like to set standardized thresholds for classifying sentences as either positive, neutral, or negative.
- Typical threshold values  are:
    1. positive sentiment: compound score >= 0.05
    2. neutral sentiment: (compound score > -0.05) and (compound score < 0.05)
    3. negative sentiment: compound score <= -0.05
- The `pos, neu, and neg scores` are ratios for proportions of text that fall in each category (so these should all add up to be 1... or close to it with float operation). These are the most useful metrics if you want to analyze the context & presentation of how sentiment is conveyed or embedded in rhetoric for a given sentence

---



---
# Sentiment Analysis for Customer Reviews

## Introduction
- In the current times with tech being the backborn of everything, organization/business are able to generate more messages especially from their customer's feedback about the product they are offering.
- Being able to analyse these feedback manually is very time consuming and inefficient. 
- To be able to address this, this project aims at developing an automated machine learning tool to categorize customer feedback into positive, negative, or neutral sentiments, providing enhanced business insights. 
- For this project, Flipkart dataset from Kaggle was selected as it contains detailed information about product reviews.


## Dataset Information 
- The datset for this project is scrapped from flipkart.com site containing information about various products from Flipkart, including electronics, clothing, home decor items, automated systems, and more. 
- As while during crawling, the flipkart has implimneted rate limiting, we were able to collect few samples about 12k records.
- A total of 9 attributed for each product was crawed. These attributes include;
    1. product_id: Contains information of product identifier, 
    2. product_title: This is the title of the product used, 
    3. rating: This is rating the current review has, 
    4. summary: This is the review summary or title of the review, 
    5. review: This is the actual review text,
    6. location: Location of the user who reviewied, 
    7. date: Date of review, 
    8. upvotes and downvotes: Number of downvote or upvote for the review,
    
- Beside the above attributes which were directly scrapped from the website, we also The sentiment labels (positive, neutral, and negative) were assigned based on the review summary using NLP techniques and manual verification (VADER TOOL WAS USED FOR THIS CASE).



## Objective
- We have the main objective of building an automated system to classify customer reviews into positive, negative, or neutral sentiments. 
- Through this, businesses can quickly gain insights into customer opinions and improve their products and services accordingly.

## Models Used
We trained four models to classify the sentiments:
1. **BERT**: A transformer-based model.
2. **RoBERTa**: An optimized version of BERT.
3. **XGBoost**: A gradient boosting model.
4. **Logistic Regression**: A simple model that uses logic function.


## Methodology
1. **Data Preprocessing**: Main focus was on the summary and sentiment columns from the dataset.
2. **Data Splitting**: The data was split into training (60%), validation (20%), and testing (20%) sets.
3. **Feature Extraction**: For XGBoost and Logistic Regression, we used CountVectorizer to convert text data into numerical features. BERT and RoBERTa models used their own tokenizers and embeddings.
4. **Model Training**: We trained BERT, RoBERTa, XGBoost, and Logistic Regression models on the training data.
5. **Performance Evaluation**: The models were evaluated using accuracy, F1 score, precision, recall, and confusion matrices.

## Future Work
- **Fine-Tuning**: Further fine-tuning of the transformer models to improve performance.
- **Feature Engineering**: Exploring additional features that may enhance model accuracy.
- **Deployment**: Creating a web application or API for real-time sentiment analysis of customer reviews.

## References
- [Flipkart Product Customer Reviews from Website](flipkart.com)
- [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)
- [RoBERTa: A Robustly Optimized BERT Pretraining Approach](https://arxiv.org/abs/1907.11692)
- [XGBoost: A Scalable Tree Boosting System](https://arxiv.org/abs/1603.02754)
- 


---


---

### 📊 Model Performance Comparison

| Model                | Accuracy | F1 Score | Precision | Recall   | Misclassification Count | Percentage Misclassification |
|----------------------|----------|----------|-----------|----------|-------------------------|-----------------------------|
| Base Logistic Regression | 0.826502 | 0.835143 | 0.846477  | 0.826502 | 309                     | 0.173498                    |
| XGBOOST CLF          | 0.871421 | 0.865561 | 0.864902  | 0.871421 | 229                     | 0.128579                    |
| ROBERTA CLF          | 0.870859 | 0.889150 | 0.909202  | 0.870859 | 230                     | 0.129141                    |
| BERT CLF             | 0.876474 | 0.894820 | 0.913956  | 0.876474 | 220                     | 0.123526                    |

### 📝 Conclusion

The BERT classifier outperformed the other models with the highest accuracy of 0.876474, F1 Score of 0.894820, and the lowest percentage of misclassification at 0.123526. The ROBERTA classifier also performed well, particularly in terms of F1 Score and Precision. The XGBOOST classifier achieved a balance between accuracy and misclassification, making it a strong contender, while the Base Logistic Regression model had the lowest performance across the board.

These results demonstrate the effectiveness of advanced models like BERT and ROBERTA in sentiment analysis tasks, especially when compared to traditional machine learning methods.


## ACCESS REPOSITORY
---
[Semintiment Analysis FlipKart Repository](https://github.com/Stephen-Kamau/Flipkart_Scraping_and_sentiment_analysis)

---