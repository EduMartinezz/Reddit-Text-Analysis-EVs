# 🔋 Reddit Text Analysis: Electric Vehicles (EVs) — Research Upgrade

This project analyzes public discussions about **Electric Vehicles (EVs)** on Reddit using **Natural Language Processing (NLP)**.  
It demonstrates **end-to-end text analytics**: scraping data from Reddit, sentiment analysis, topic modeling, word clouds, and interactive visualizations.  

The app is built with **Streamlit** and integrates **modern NLP models** (Transformers, BERTopic) while keeping **lightweight fallbacks** (VADER, LDA) so it can run in any environment.

---

## 📖 Project Overview
- Scrapes live Reddit posts (via **PRAW API**) on EV-related queries.  
- Performs **sentiment analysis** using:
  - ⚡ Transformer (`cardiffnlp/twitter-roberta-base-sentiment-latest`)  
  - 🪶 VADER (fallback if Transformers unavailable)  
- Performs **topic modeling** using:
  - 🔍 BERTopic (embedding + clustering)  
  - 📊 LDA (fallback if BERTopic unavailable)  
- Includes **visualizations**:
  - Sentiment class balance  
  - Sentiment distribution & trends over time  
  - Word clouds of EV discussions  
  - Topic keywords per cluster  
- Interactive dashboard with **query inputs, controls, downloads**.

---

## 📊 Example Outputs

### 🔎 Query Interface
Fetch live posts from subreddits like `r/electricvehicles` or `r/cars` with custom queries (e.g., `EV OR Tesla OR Electric Vehicle`).
- https://github.com/EduMartinezz/Reddit-Text-Analysis-EVs/blob/main/Reddit_dash.PNG
- https://github.com/EduMartinezz/Reddit-Text-Analysis-EVs/blob/main/Reddit_dash1.PNG

### 📈 Sentiment Analysis
- Distribution of **positive / neutral / negative** posts  
- Score histogram  
- **Trend of average sentiment** over months/years  
- Examples of posts per sentiment

### ☁️ Word Cloud
Most frequent terms in EV-related Reddit posts.

- https://github.com/EduMartinezz/Reddit-Text-Analysis-EVs/blob/main/Reddit_dash2.PNG
- https://github.com/EduMartinezz/Reddit-Text-Analysis-EVs/blob/main/Reddit_dash3.PNG
- https://github.com/EduMartinezz/Reddit-Text-Analysis-EVs/blob/main/Reddit_dash4.PNG


### 🧩 Topic Modeling
- **BERTopic** (if installed): coherent clusters with contextual embeddings  
- **LDA** fallback: keyword-based topics  

---

## 🛠️ Tech Stack
- **Python**  
- **Libraries:**
  - `streamlit` — interactive dashboard  
  - `praw` — Reddit API wrapper  
  - `nltk` — VADER sentiment  
  - `transformers`, `torch` — RoBERTa sentiment  
  - `bertopic`, `sentence-transformers`, `umap-learn`, `hdbscan` — advanced topic modeling  
  - `scikit-learn` — preprocessing + LDA  
  - `matplotlib`, `wordcloud` — visualization  

---

## 🚀 Setup & Run

### 1. Clone Repository
'''bash
git clone https://github.com/your-username/reddit-ev-nlp.git
cd reddit-ev-nlp


### 2. Install Requirements
Light install (runs VADER + LDA):
pip install -r requirements.txt

Full install (Transformer + BERTopic):
pip install streamlit praw wordcloud scikit-learn nltk matplotlib transformers torch bertopic umap-learn hdbscan sentence-transformers


### 3. Set Reddit API Keys
Get your credentials from [Reddit Apps](https://www.reddit.com/prefs/apps)
- client_id
- client_secret
- user_agent

### 4. Run the App
streamlit run app_ev_reddit.py

## If using Google Colab, expose with ngrok:
from pyngrok import ngrok
ngrok.set_auth_token("YOUR_TOKEN")
print(ngrok.connect(8501))

## 📂 Project Structure
📦 reddit-ev-nlp
 ┣ 📜 app_ev_reddit.py        # Streamlit dashboard
 ┣ 📜 requirements.txt        # dependencies
 ┣ 📜 README.md               # documentation
 ┗ 📂 screenshots             # optional saved screenshots


## 📈 Example Results (from demo queries)
**Sentiment balance**: majority neutral, with strong positive spikes around affordability and innovation.
**Word cloud**: "Tesla", "battery", "charging", "range", "market", "transition".
**Topics (BERTopic):**
- Market trends, EV adoption, sales
- Charging infrastructure, models, plans
- Energy transition & road trips
- Affordability & incentives

## ✨ Key Features for Portfolio
**API Integration** (Reddit via PRAW)
**Modern NLP** (Transformers, BERTopic)
**Interactive Visualization** (Streamlit + wordclouds + charts)
**Research-Grade Upgrade**: fallback support ensures reproducibility in lightweight environments.
