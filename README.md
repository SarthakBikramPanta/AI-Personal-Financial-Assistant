# 🧠 AI Personal Financial Assistant (NLP)

A high-performance Natural Language Processing pipeline that performs real-time sentiment analysis on financial news to predict market signals. This project leverages **FinBERT**, a specialized Transformer model pre-trained on over 10,000 financial reports.

![Dashboard Screenshot](images/dashboard_screenshot.png)

## 🚀 Overview
Traditional sentiment analysis often fails in the financial sector (e.g., the word "crude" is negative in general text but neutral/specific in energy markets). This assistant solves that by using **Transfer Learning** on a domain-specific model to provide actionable market insights.

### Key Features:
- **Live Data Ingestion:** Real-time news scraping via the Yahoo Finance API.
- **GPU-Accelerated Inference:** Uses Hugging Face `pipelines` with PyTorch for batch processing.
- **Quantitative Mapping:** Converts qualitative sentiment into a numerical "Weighted Score" (Confidence × Sentiment).
- **Market Alignment Check:** Compares AI predictions against actual intra-day price movements.

## 🛠️ Tech Stack
- **Language:** Python 3.x
- **Environment:** Google Colab / Jupyter
- **ML Frameworks:** Transformers (Hugging Face), PyTorch
- **Data & Viz:** YFinance, Pandas, Plotly (Interactive Charts)

## 📊 Methodology
1. **Extraction:** Headlines are fetched using `yfinance.Ticker.news`.
2. **Analysis:** The `ProsusAI/finbert` model classifies text into *Positive*, *Negative*, or *Neutral*.
3. **Signal Generation:** A custom logic calculates a **Market Vibe** score:
   - `> 0.2`: Strongly Bullish
   - `< -0.2`: Strongly Bearish
4. **Validation:** The script pulls 5-day historical price data to verify if the AI sentiment correlates with the current price trend.

## 📈 Results
The assistant successfully identifies "Leading Indicators" where news sentiment shifts before the price reflects the change, providing a potential edge in automated trading strategies.

## 📂 How to Run
1. Open the notebook in [Google Colab](https://colab.research.google.com/drive/1ItvsCnoWz-C6yS9JuipUaXZylUXPoXSj?usp=sharing/).
2. Install dependencies: `pip install transformers yfinance plotly`.
3. Enter any stock ticker (e.g., `AAPL`, `TSLA`, `NVDA`) to generate a new report.
