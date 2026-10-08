# Flipkart Review Sentiment Studio

A Streamlit web app that predicts whether a Flipkart product review is **positive**, **negative**, or **neutral**. Write a review on the first screen and view the prediction on a separate results screen.

## Features

- Sentiment prediction using a trained LinearSVC model and TF-IDF vectorizer
- Review text cleaning before prediction
- Two-step, animated interface with a separate results screen
- Responsive layout for desktop and mobile

## Project files

```text
.
├── app.py
├── requirements.txt
├── flipkart_sentiment_svm.joblib
├── flipkart_sentiment_tfidf.joblib
└── Flipkart_Product_reviews_with_sentiment_Dataset.ipynb
```

The model and vectorizer files are required by the app and should stay in the same folder as `app.py`. The notebook contains the dataset exploration and model training workflow. The web app uses the saved model files and does not download the dataset when it starts.

## Setup on Windows

Open PowerShell in the project folder and create a virtual environment:

```powershell
python -m venv .venv
```

Activate it:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks script activation, you can install and run the app without activating the environment:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Otherwise, install the dependencies and start Streamlit:

```powershell
python -m pip install -r requirements.txt
streamlit run app.py
```

Streamlit will print a local URL in the terminal, usually `http://localhost:8501`. Open it in your browser.

## Try a prediction

Paste a review into the first screen and select **Find the feeling**. For example:

```text
Amazing product, excellent quality and fast delivery. I am very happy with this purchase.
```

The result screen shows the predicted sentiment. Select **Analyze another review** to try another one.

## Model compatibility

The saved model artifacts were created with scikit-learn **1.6.1**, so `requirements.txt` pins scikit-learn to that version for compatibility.
