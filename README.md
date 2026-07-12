 Email Spam Detection System using Machine Learning

An end-to-end Machine Learning and Natural Language Processing (NLP) pipeline built in Python to accurately classify emails into **Spam** or **Ham (Safe)**. This project includes comprehensive Exploratory Data Analysis (EDA), text preprocessing, feature engineering, and deployment readiness using Streamlit.

Project Overview & Highlights
High Precision Modeling: Evaluated multiple classification models, with Multinomial Naive Bayes emerging as the top performer for text classification.
Streamlit Web UI Ready:Structured to be easily deployed as an interactive web application where users can paste any email text for real-time predictions.
Production-Grade Pipeline:** Incorporates robust data cleaning, duplicate removal, text normalization, and vectorization techniques.

ech Stack & Libraries
Language:Python
Data Processing & EDA: Pandas, NumPy, Matplotlib, Seaborn
Natural Language Processing (NLP):** NLTK (Tokenization, Stopwords, WordNet Lemmatizer)
Machine Learning:** Scikit-Learn (LabelEncoder, TF-IDF Vectorizer, train_test_split, MultinomialNB, Metric evaluations)

 Pipeline Architecture & Steps
1. Data Cleaning
* Dropped redundant/unnamed tracking columns.
* Handled the severe class imbalance (4,516 Ham vs. 653 Spam samples).
* Removed **403 duplicate rows** to prevent data leakage during validation.
* Encoded categorical labels (`ham` -> 0, `spam` -> 1) using `LabelEncoder`.

2. Exploratory Data Analysis (EDA)
* Engineered text-length features: `num_characters`, `num_words`, and `num_sentences` using NLTK tokenizers.
* Visualized distributions using Seaborn Histograms, Pairplots, and Heatmaps, proving that **Spam messages significantly contain more characters and words** than regular Ham messages.

3. Text Preprocessing
Created a specialized `clean_texts` function that performs:
* Lowercasing & Punctuation removal via Regex (`[^a-z\s]`).
* URL and link filtering.
* Stop-words elimination (using NLTK English corpus).
* **WordNet Lemmatization** to reduce words to their base dictionary forms.

4. Feature Extraction & Modeling
* Converted processed text into numerical matrices using **TF-IDF Vectorization** (restricted to top 3,000 features).
* Split the dataset using a **Stratified Train-Test Split (80/20)** to maintain class proportions.
* Trained a **Multinomial Naive Bayes** classifier, yielding excellent accuracy and precision metrics perfectly suited for filtering out malicious spam.

 How to Run Locally
Using Streamlit
Clone the repository:
Check the live ML model on Hugging Face:
https://tazeenzahrabatool-email-spam-detector.hf.space/?logs=container&__theme=system&deep_link=fQgMCFV57Y0
