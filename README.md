<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E1B4B,25:312E81,50:4C1D95,75:6D28D9,100:A855F7&height=220&section=header&text=Calculative%20Foundation&fontSize=52&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Exploring%20the%20Mathematics%20Behind%20Modern%20Data%20Analysis&descAlignY=58&descSize=20"/>

A complete **Theory + Practical Statistics Project** applying **Probability Distributions** to a real-world **financial transaction dataset** containing customer purchase records.  

This project demonstrates how to **understand and apply distribution concepts** to model transaction behaviors, handle skewed data, and derive actionable business insights.

---

## 🎯 Objective

An **e-commerce platform** wants to analyze **daily transaction amounts** to understand customer purchase behavior.  
Key goals:  
- Identify which **statistical distributions** fit transaction data.  
- Handle **skewness and variance** using transformations.  
- Derive **probability-based insights** for fraud detection, demand forecasting, and revenue modeling.  

---

## 🗂️ Project Files

| File | Description |
|------|-------------|
| 📓 **spread_locator.ipynb** | Complete Probability Distribution Analysis |
| 📊 **spread_locator_dataset.xlsx** | Financial transaction dataset |
| 📄 **Probability_Distributions_Theory.pdf** | Theory, formulas, and explanations |
| 🖼️ **Diagrams/** | Distribution diagrams and illustrations |
| 📘 **README.md** | Project documentation |

---

## 🛠️ Tools Used
- **Python (Jupyter Notebook)**  
- Libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy.stats`, `statsmodels`

---

## 📗 Theory Topics Covered
- Q-Q Plot and its role in normality testing  
- Discrete vs Continuous distributions  
- Bernoulli Distribution & Binomial Distribution  
- Log-Normal Distribution  
- Power Law Distribution  
- Box-Cox Transformation  
- Poisson Distribution  
- Z-Score Probability  
- PDF vs CDF  

---

## 🔬 Practical Statistical Analysis

### 1. Bernoulli & Binomial
- Bernoulli models **success/failure** of transactions.  
- Binomial extends to **weekly counts**.  
- **Insight:** Helps forecast active transaction days → staffing & inventory planning.

### 2. Poisson Distribution
- Models **daily transaction counts**.  
- λ (mean rate) predicts demand & detects anomalies.  
- **Insight:** Supports fraud detection and cash-flow optimization.

### 3. Log-Normal & Power Law
- Transaction amounts are **right-skewed**.  
- Log-Normal fits bulk data; Power Law fits extreme tail.  
- **Insight:** Revenue forecasting + rare high-value transaction monitoring.

### 4. Q-Q Plot
- Confirms **non-normality** of transaction amounts.  
- Heavy tail deviation → skewness & outliers.  
- **Insight:** Apply transformations before parametric tests.

### 5. Box-Cox Transformation
- Stabilizes variance & reshapes skewed data.  
- **Insight:** Enables regression & forecasting with improved accuracy.

### 6. Z-Score Probability
- Standardizes transaction amounts.  
- Computes **P(amount > ₹5000)**.  
- **Insight:** Fraud detection thresholds & VIP customer identification.

### 7. PDF & CDF
- PDF shows density around mean.  
- CDF shows cumulative probabilities.  
- **Insight:** Supports percentile-based offers & pricing decisions.

---

## 🏁 Final Conclusion

### 🥇 Best-Fitting Distributions
| Variable | Best Distribution | Why |
|----------|------------------|-----|
| Transaction occurrence | **Bernoulli** | Binary success/failure |
| Weekly transaction count | **Binomial** | Sum of 7 Bernoulli days |
| Daily transactions | **Poisson** | Rare, independent events |
| Transaction amount | **Log-Normal** | Positive, skewed, multiplicative |

---

## 🧠 Key Business Insights
- 📅 **Operational Planning:** Bernoulli/Binomial → forecast active days.  
- 📈 **Demand Forecasting:** Poisson λ → predict daily volumes.  
- 💵 **Revenue & Risk:** Log-Normal → reliable revenue models.  
- 🛡️ **Fraud Detection:** Z-scores & thresholds flag anomalies.  
- 🔧 **Analytics Readiness:** Box-Cox → prepares data for parametric models.  

---

## 🚀 How to Run
1. Install libraries:  
   ```bash
   pip install pandas numpy scipy matplotlib seaborn statsmodels openpyxl
