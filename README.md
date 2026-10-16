# 📈 High Volatility Day Predictor using Machine Learning

This project aims to predict whether the next trading day will be a **high volatility day** for an ETF or stock, using technical indicators and machine learning (CatBoost). It’s built for traders or portfolio managers who want to manage risk by identifying sudden spikes in price movement.

---

## 🎯 Objective

To build a binary classification model that predicts if the next day’s price will show **high intraday volatility** (e.g., >3%).

---

## 📊 Dataset

- **Source**: [Kaggle – US Stocks & ETFs Price Volume Data](https://www.kaggle.com/datasets/borismarjanovic/price-volume-data-for-all-us-stocks-etfs)
- **File format**: `.txt` (CSV-style with columns: Date, Open, High, Low, Close, Volume)
- **Used**: A single ETF `.txt` file (e.g., SPY.txt) for simplicity

---

## ⚙️ ETL & Feature Engineering

- Loaded `.txt` file and cleaned data
- Created target label:
  - `1` = next day volatility > 3%
  - `0` = otherwise
- Feature set includes:
  - **Price features**: Open, Close, High, Low, Volume
  - **Indicators**: SMA, EMA, RSI, ATR, Bollinger Band Width
  - **Price change & return**

---

## 🧠 Model

- **Algorithm**: CatBoostClassifier (good for tabular data)
- **Imbalance handled with**: SMOTE
- **Data split**: 80/20 Train-Test, stratified
- **Scaling**: StandardScaler

---

## 📈 Results

| Metric     | Score  |
|------------|--------|
| Accuracy   | 0.77   |
| Precision  | 0.80   |
| Recall     | 0.68   |
| F1-score   | 0.73   |

✅ Model performs well in identifying high volatility days, with good balance between precision and recall.

---

## 📦 Model Export

The trained model is saved as a `.pkl` file using `joblib`:

```bash
volatility_predictor_catboost.pkl
````

---

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/your-username/volatility-predictor-ml.git
cd volatility-predictor-ml
```

### 2. Create virtual environment & install dependencies

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\\Scripts\\activate
pip install -r requirements.txt
```

### 3. Run notebook

Open `volatility_predictor.ipynb` and run all cells.

---

## 📌 Future Improvements

* Add multi-day volatility forecasting
* Build a Streamlit dashboard
* Integrate with live data APIs like yFinance or Alpaca

---

## 🧑‍💻 Author

**Aditya Kaushik**
*Built for learning, showcasing ML in finance, and risk-control modeling.*


