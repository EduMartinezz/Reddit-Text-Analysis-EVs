# Reddit Text Analysis: Electric Vehicles (EVs)

## Overview
This project analyzes public discussions about Electric Vehicles (EVs) on Reddit using advanced Natural Language Processing (NLP) techniques. The analysis includes sentiment analysis, topic modeling, and visualizations to gain insights into user perceptions, trends, and preferences regarding EVs.

---

## Features
- **Data Collection**:
  - Scrape Reddit posts and comments about EVs using keywords like `Tesla`, `Nissan Leaf`, and `Chevrolet Bolt`.
- **Text Preprocessing**:
  - Tokenization, stemming, and removal of stopwords.
- **Sentiment Analysis**:
  - Determine the sentiment of posts and comments using:
    - `TextBlob` for basic polarity scoring.
    - `BERT` for advanced sentiment classification.
- **Topic Modeling**:
  - Discover latent topics with LDA (Latent Dirichlet Allocation).
- **Visualizations**:
  - Word Cloud, Sentiment Timeline, and Interactive Topic Visualizations.
- **Interactive Dashboard**:
  - A user-friendly Streamlit app for real-time analysis and exploration.

---

## Dataset
The dataset consists of posts and comments collected from Reddit using the following keywords:
- `Battery Electric Vehicle (BEV)`
- `Tesla Model 3`
- `Chevrolet Bolt`
- `Nissan Leaf`
- `Electric Vehicle (EV)`

The collected data includes:
- Titles and bodies of posts.
- Comments under each post.
- Timestamps of posts and comments.

---

## Project Structure

Reddit-Text-Analysis/
│
├── src/
│   ├── collect_reddit_data.py      # Handles Reddit API calls
│   ├── preprocess_text.py          # Preprocesses text
│   ├── eda.py                      # Explores data and visualizations
│   ├── modeling.py                 # Topic modeling and sentiment analysis
│   ├── visualizations.py           # Interactive visualizations
│
├── data/
│   ├── raw/                        # Raw collected data
│   ├── processed/                  # Preprocessed data
│
├── outputs/
│   ├── visualizations/             # Graphs, charts, etc.
│   ├── results.csv                 # Results or predictions
│
├── notebooks/
│   ├── analysis_demo.ipynb         # Interactive notebook for showcasing results
│
├── README.md                       # Documentation
├── requirements.txt                # Dependencies
├── .gitignore                      # Ignored files
├── main.py                         # Main script


## Installation

### Prerequisites
1. **Python**: Version 3.8 or above.
2. **Reddit API Credentials**:
   - Create an app on the [Reddit Developer Portal](https://www.reddit.com/prefs/apps).
   - Obtain your `client_id`, `client_secret`, and `user_agent`.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/Reddit-Text-Analysis-EVs.git
   cd Reddit-Text-Analysis-EVs

2. ### Install dependencies
pip install -r requirements.txt

3. ### Configure Reddit API credentials:
   - Open main.py and update the credentials:
   - reddit = initialize_reddit("your_client_id", "your_client_secret", "your_user_agent")

4. ### Run the main script:
   - python main.py
5. ### Launch the Streamlit Dashboard:
   - streamlit run streamlit_app.py


### Usage
**Data Collection**
- Modify the search term in main.py to customize the analysis
- search_term = "Battery Electric Vehicle OR Tesla OR Nissan Leaf OR Electric Vehicle"

### Preprocessing
- Data is automatically cleaned and preprocessed during the pipeline execution.

**Example Code Snippet**
To fetch data from Reddit and preprocess it
from collect_reddit_data import initialize_reddit, fetch_reddit_data
from preprocess_text import preprocess_text

# Initialize Reddit API
reddit = initialize_reddit("client_id", "client_secret", "user_agent")

# Fetch data
search_term = "Electric Vehicle OR Tesla"
raw_data = fetch_reddit_data(reddit, search_term, limit=100)

# Preprocess data
processed_data = [preprocess_text(item['text']) for item in raw_data]


### Analysis
## Insights 
**Sentiment Analysis:**
  - Sentiment scores (Positive, Negative, Neutral) are calculated and stored.
  - Majority of posts about Tesla are Positive.
  - Discussions around EV charging infrastructure tend to be Neutral or Negative.

**Trending Topic:** 
  - Common topics include battery range, charging speed, and pricing.

**Popular Keywords:**
  - Tesla, Nissan, Bolt, Battery, Charging.

### Visualizations
**Word Cloud:** Visualize the most frequent words.
**Sentiment Timeline:** Track sentiment trends over time.
**Interactive Topic Visualization:** Explore topics interactively with pyLDAvis.

## Output Examples
1. Word Cloud

2. Sentiment Timeline

3. Interactive Topics



### Testing
Run unit tests:
- pytest tests/


### Future Improvements
- Add Named Entity Recognition (NER) for brand and product mentions.
- Deploy the Streamlit app for public access.
- Use RoBERTa or GPT-based sentiment analysis for improved accuracy.

