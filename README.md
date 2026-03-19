# User Behavior Prediction on Social Media

Predict user behavior patterns on Platform X (Twitter) based on engagement metrics, using machine learning and an interactive Streamlit dashboard.

---

## Overview

This project collects tweet data from a target user via the Twitter API, preprocesses and stores it in MongoDB, trains a Random Forest model to predict engagement behavior, and visualizes the results through a Streamlit web app.

---

## Architecture

```
Twitter API (Tweepy)
      ↓
Data Collection (thuthap.py)
      ↓
MongoDB Storage (MongoDB.py)
      ↓
Preprocessing & Feature Engineering (tienxuly.ipynb)
      ↓
Model Training — Random Forest (Random Forest.ipynb)
      ↓
Streamlit Dashboard (Streamlit/)
```

---

## Features

- **Data Collection:** Fetches up to 100 tweets per request including text, engagement metrics (likes, retweets, replies, quotes), media attachments, hashtags, mentions, and URLs via Tweepy
- **Media Download:** Automatically downloads images and videos attached to tweets using `requests` and `yt-dlp`
- **Storage:** Stores raw tweet data in MongoDB for flexible, unstructured data handling
- **Preprocessing:** Cleans and transforms raw data — handles missing values, encodes categorical features, and engineers engagement-based features
- **Modeling:** Trains a Random Forest classifier to predict user behavior patterns based on post characteristics
- **Dashboard:** Interactive Streamlit app for real-time visualization and exploration of prediction results

---

## Project Structure

```
├── thuthap.py               # Data collection via Twitter API
├── MongoDB.py               # MongoDB connection and storage
├── tienxuly.ipynb           # Data preprocessing & feature engineering
├── Random Forest.ipynb      # Model training & evaluation
├── Streamlit/               # Streamlit dashboard app
├── model/                   # Saved model files
└── Data.rar                 # Raw dataset
```

---

## Tech Stack

- **Language:** Python
- **Data Collection:** Tweepy, Requests, yt-dlp
- **Storage:** MongoDB
- **Processing:** Pandas, NumPy
- **Modeling:** Scikit-learn (Random Forest)
- **Visualization:** Streamlit, Matplotlib, Seaborn

---

## Setup

### 1. Install dependencies

```bash
pip install tweepy pandas pymongo scikit-learn streamlit yt-dlp requests
```

### 2. Configure Twitter API credentials

In `thuthap.py`, fill in your credentials:

```python
BEARER_TOKEN = 'your_bearer_token'
USERNAME = 'target_username'
```

### 3. Collect data

```bash
python thuthap.py
```

### 4. Store data in MongoDB

```bash
python MongoDB.py
```

### 5. Preprocess & train model

Run the notebooks in order:
1. `tienxuly.ipynb`
2. `Random Forest.ipynb`

### 6. Launch dashboard

```bash
cd Streamlit
streamlit run app.py
```
