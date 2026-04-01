# 🧠 AI Personal Financial Assistant (NLP)

An end-to-end sentiment analysis pipeline that uses **FinBERT** (a specialized Transformer model) to analyze real-time financial news and predict market "vibes."

---

## 🚀 Project Overview
This project bridges the gap between raw financial news and actionable market intelligence. Unlike standard sentiment models, this uses a model pre-trained on **4.9 billion words** of financial text to understand nuances like "crude," "bullish," and "volatility."

### Key Features:
* **Live Data Extraction:** Pulls real-time news headlines via the `yfinance` API.
* **GPU-Accelerated Inference:** Uses Hugging Face pipelines with CUDA optimization for fast text processing.
* **Interactive Dashboard:** Visualizes sentiment distribution using `Plotly`.
* **Market Validation:** Compares AI-generated "Weighted Sentiment Scores" against actual 5-day stock price movements.



---

## 🛠️ Tech Stack
* **Language:** Python 3.10+
* **AI Model:** [ProsusAI/finbert](https://huggingface.co/ProsusAI/finbert) (Transformer-based)
* **Libraries:** `transformers`, `torch`, `yfinance`, `pandas`, `plotly`
* **Environment:** Google Colab / Jupyter Notebooks

---

## 📊 How it Works
The assistant follows a 3-stage intelligence pipeline:

1.  **Extraction:** Scrapes the latest headlines for a given ticker (e.g., NVDA, AAPL).
2.  **Analysis:** Each headline is passed through the FinBERT model to calculate a probability score for *Positive*, *Negative*, or *Neutral* sentiment.
3.  **Synthesis:** Calculates a **Weighted Sentiment Score** where:
    $$\text{Weighted Score} = \text{Sentiment Value} \times \text{Confidence Level}$$
    A final "Market Signal" is generated based on the mean score of all news items.

---

## 📂 How to Run
1. Open the notebook in [Google Colab](https://colab.research.google.com/drive/1ItvsCnoWz-C6yS9JuipUaXZylUXPoXSj?usp=sharing/).
2. Install dependencies: `pip install transformers yfinance plotly`.
3. Enter any stock ticker (e.g., `AAPL`, `TSLA`, `NVDA`) to generate a new report.
