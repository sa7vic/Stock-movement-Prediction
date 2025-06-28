# 📊 Stock Market Movement Prediction Using Machine Learning

Predict the **next-day stock price movement** (up/down) using financial data and classification models. This project explores feature engineering, exploratory analysis, and model comparison across tech stocks: **AAPL, GOOG, MSFT, and AMZN**.

---

## 🔧 Highlights

- Cleaned & analyzed historical stock data
- Engineered features like:
  - Daily returns
  - Moving averages (10, 20, 50 days)
- Applied outlier handling (Z-score, IQR)
- Balanced target using **SMOTE** & **ADASYN**

---

## 📈 Data Insights

- 📉 **Moving Averages**: Help spot trends  
- 📊 **Return Histograms**: Most returns cluster near 0  
- 📈 **Risk-Return**:
  - GOOG → High return, high risk
  - AAPL → Low return, low risk  
- 🔗 **Correlations**: Strong in prices, moderate in returns — useful for diversification

---

## 🤖 Models & Results

| Model         | Accuracy | Precision | AUC    |
| ------------- | -------- | --------- | ------ |
| Decision Tree | 40.16%   | 0.75      | 0.5090 |
| Random Forest | 40.16%   | 0.75      | 0.5154 |

✅ **Random Forest** slightly outperformed — preferred model for this task.

---

## 📁 Folder Structure

```

Stock-Movement-Prediction/
├── CSV/
│   ├── AAPL.csv
│   ├── GOOG.csv
│   ├── MSFT.csv
│   └── AMZN.csv
├── Stock\_Prediction\_Movement.ipynb
└── README.md

````

---

## 🚀 Run the Notebook

1. Clone the repo:
   ```bash
   git clone https://github.com/sa7vic/stock-movement-prediction.git
   cd stock-movement-prediction
   ```

2. Install requirements (you can also use a virtual environment):

   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

4. Open `Stock_Prediction_Movement.ipynb` and run cells step by step.

✅ Make sure the stock CSV files are inside the `CSV/` folder.

---

## 🛠️ Future Enhancements

* Use **LSTM or Transformer** models for time series forecasting
* Add **live data** via API (e.g., Alpha Vantage, Yahoo Finance)
* Deploy as a **Streamlit app** for interactive predictions

---

## 👨‍💻 Author

**Sourav Kumar**

*Machine Learning & Financial Modeling Enthusiast*

---

## 📄 License

MIT — free to use, share, and improve.
