# RoboReviews-Project

Robo Reviews Project
Overview
The Robo Reviews Project is a product review aggregator system that uses machine learning and natural language processing (NLP) techniques to classify customer reviews into sentiments (positive, neutral, or negative) and organize them into various product meta-categories. The project also generates blog-style content that summarizes reviews and identifies key insights such as top-rated products, complaints, and worst products.

Features
Sentiment Classification: Classifies customer reviews into three sentiments:
Positive
Neutral
Negative

Meta-Category Classification: Groups product reviews into predefined meta-categories such as:

Ebook Readers
Batteries
Accessories
Tablets
Non-Electronics

Blog-Style Summaries: Automatically generates blog-style content based on product categories, including:

Top 3 products
Worst product
Common complaints from negative reviews
Differences between top products

BERT Sentiment Analysis: Uses the pre-trained BERT model to predict the sentiment of customer reviews and fine-tunes it on the provided dataset.

Dataset Used
The dataset contains Amazon product reviews with the following relevant columns:

reviews.text: The customer review text.
reviews.rating: The star rating (1-5) provided by the customer.
categories: The product categories (e.g., Electronics, Health & Beauty).
reviews.username: The username of the customer.
reviews.date: The date when the review was posted.
Sample dataset header:


id, dateAdded, dateUpdated, name, asins, brand, categories, primaryCategories, imageURLs, reviews.numHelpful, reviews.rating, reviews.sourceURLs, reviews.text, reviews.title, reviews.username, sourceURLs, reviews.dateAdded, reviews.userCity, reviews.userProvince

Project Workflow

1. Preprocessing
Cleaning: Removing unwanted characters, lowercasing, and tokenizing the review text.
Handling Missing Values: Dropping rows where reviews.text or reviews.rating is missing.
Sentiment Labeling: Using reviews.rating to label reviews as positive, neutral, or negative.

3. Sentiment Classification with BERT
Tokenizing the cleaned review text using BERT tokenizer.
Fine-tuning the BERT model to classify review sentiment.
Classifying sentiments into positive, neutral, or negative using the fine-tuned model.

4. Meta-Category Classification
Categorizing products based on keywords in the categories column.
Assigning meta-category labels (e.g., Ebook Readers, Batteries) using predefined keywords.

5. Blog-Style Article Generation
Summarizing Reviews: Using the BART model to generate summaries for each meta-category.
Top Products Identification: Identifying the top 3 products based on average rating and review count.
Worst Product Identification: Selecting the product with the lowest rating.
Complaints Extraction: Extracting the most common complaints from negative reviews.

6. Model Evaluation
Evaluating model performance using accuracy, F1-score, precision, and recall.
How to Use
Step 1: Clone the Repository

git clone https://github.com/SaiqaMehdi/RoboReviews-Project/.git
cd RoboReviews-Project

Step 2: Install Required Libraries
Install the necessary libraries using pip:
pip install -r requirements.txt

Requirements
The project requires the following libraries:

pandas
numpy
scikit-learn
transformers
torch
nltk
flask
Ensure that these libraries are installed before running the project.

Model Training
You can fine-tune the BERT model for sentiment classification and the XLNet model for meta-category classification by following the steps in the main.ipynb Jupyter notebook
