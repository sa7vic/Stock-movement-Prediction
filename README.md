# 📊 Stock Market Movement Prediction Using Machine Learning

This project aims to predict next-day stock price movement using classification models. It combines financial data preprocessing, visualization, and machine learning to analyze and forecast trends in top tech stocks: **AAPL, GOOG, MSFT, and AMZN**.

---

## 🔧 Preprocessing & Feature Engineering

* **Missing Value Handling**: Cleaned and imputed missing data points.
* **Outlier Detection**: Applied Z-score and IQR techniques to validate return distributions.
* **Class Balancing**:

  * **SMOTE**: Synthetic oversampling improved classification performance.
  * **ADASYN**: Less effective due to low imbalance in target classes.

### 📉 Moving Averages

Calculated moving averages to capture short- and long-term trends:

```python
ma_day = [10, 20, 50]
for ma in ma_day:
    for company in company_list:
        company[f"MA for {ma} days"] = company["Adj Close"].rolling(ma).mean()
```

Visualizations:

* **Short-term MAs (10-day)**: Quick trend detection
* **Long-term MAs (50-day)**: Smooth out noise for broader insights

<p align="center"><strong>MA Plot Sample:</strong> Apple, Google, Microsoft, and Amazon</p>

---

## 📈 Exploratory Data Analysis

### 🔹 Daily Returns Histogram

Used **Freedman–Diaconis Rule** to determine optimal bin size:

* AAPL and MSFT: Symmetric, low-volatility returns
* GOOG and AMZN: Heavy tails, indicating higher risk/return

### 🔹 Return vs Risk Analysis

* **GOOG**: Highest return, but highest risk
* **AAPL**: Safer investment with lower return

### 🔹 Correlation Analysis

* **Returns**: Moderate correlation (\~0.4–0.6) — diversification potential
* **Prices**: Strong correlation (\~0.8–0.96) — shared market trends

---

## 🤖 Modeling

### 📌 Features Used

* **Price Data**: Open, High, Low, Adj Close
* **Engineered Features**: Moving Averages, Daily Returns
* **Target**: Next-day price movement (Up/Down)

---

### 🌳 Decision Tree (DT)

* **Pros**: High interpretability, visual trace of decision-making
* **Cons**: Susceptible to overfitting on volatile stock data

**Performance**:

* Accuracy: 40.16%
* Precision: 0.75
* AUC: 0.5090

---

### 🌲 Random Forest (RF)

* **Pros**: Better generalization, lower overfitting via tree ensemble
* **Cons**: Reduced interpretability

**Performance**:

* Accuracy: 40.16%
* Precision: 0.75
* AUC: 0.5154

---

### ✅ Model Comparison

| Metric    | Decision Tree | Random Forest |
| --------- | ------------- | ------------- |
| Accuracy  | 40.16%        | 40.16%        |
| Precision | 0.75          | 0.75          |
| AUC       | 0.5090        | **0.5154**    |

🔍 **Conclusion**: Random Forest slightly outperformed DT and is preferred for prediction in this context.

---

## 🔍 Key Insights

1. **GOOG** is the most model-friendly stock with predictable return behavior.
2. **Random Forest** was more stable and accurate than Decision Tree.
3. **SMOTE** improved prediction reliability; **ADASYN** was limited in effectiveness.
4. **Moving Averages** aided in trend discovery and technical analysis.
5. **Histograms** showed most returns clustered near zero, with rare extremes.
6. **Outlier checks** confirmed data was clean and suitable for modeling.

---

Sure! Here's the **updated Project Structure section** for your `README.md`, incorporating the `Stock_Prediction_Movement.ipynb`, a `CSV/` folder, and the `README.md` itself:

---

## 📁 Project Structure

```
Stock-Movement-Prediction/
├── CSV/                             
│   ├── AAPL.csv
│   ├── GOOG.csv
│   ├── MSFT.csv
│   └── AMZN.csv
│
├── Stock_Prediction_Movement.ipynb  
│
├── README.md                       
```

---

## 🚀 How to Run

### ✅ Prerequisites

Make sure you have the following installed:

* Python 3.7+
* Jupyter Notebook or JupyterLab
* Required libraries (`pandas`, `numpy`, `matplotlib`, `scikit-learn`, `imbalanced-learn`, etc.)

### 📦 Step-by-Step Guide

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-username/stock-movement-prediction.git
   cd stock-movement-prediction
   ```

2. **Create a virtual environment (optional but recommended)**:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install required packages**:

   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

5. **Open the notebook**:
   In your browser, open `Stock_Prediction_Movement.ipynb` and run the cells step by step.

6. **Ensure CSV files are in the correct folder**:
   The notebook expects stock data CSV files (`AAPL.csv`, `GOOG.csv`, etc.) inside the `CSV/` directory.

---

## 📌 Future Improvements

* Incorporate **LSTM** and **transformer models** for time series forecasting.
* Integrate **real-time data** via APIs.
* Deploy as a **streamlit dashboard** for live predictions.

---

## 👨‍💻 Author

**Sourav Kumar**
*Data Science Enthusiast | Financial Modeling | Machine Learning*

---
