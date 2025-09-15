# 📱 Bayesian Analysis of Mobile Device User Behavior
This project, developed for a Bayesian Data Analysis course, aims to predict a user's mobile device usage behavior by classifying them into one of two categories: high-frequency or low-frequency users. The analysis utilizes the **"Mobile Device Usage and User Behavior Dataset"** to build and compare two Bayesian regression models for binary classification.

The core objective is to evaluate the performance of **Logistic Regression (with a logit link)** against **Probit Regression (with a probit link)**. The comparison is based on posterior estimates, model convergence diagnostics (ESS, Gelman-Rubin, Geweke), and predictive accuracy metrics (DIC and WAIC).

---

### 📊 Dataset & Preprocessing
The dataset contains 700 observations with 11 variables.
* **Features:** `Device Model`, `Operating System`, `App Usage Time`, `Screen On Time`, `Battery Drain`, `Number of Apps Installed`, `Data Usage`, `Age`, and `Gender`.
* **Target Variable:** `User Behavior Class` that transformed from a multi-class (0-4) to a binary class:
  * **0 (Low Usage):** Original classes 0, 1, 2.
  * **1 (High Usage):** Original classes 3, 4.

---

### ⚙️ Bayesian Modeling & Methodology
To classify user behavior, two Bayesian models were implemented using **Markov Chain Monte Carlo (MCMC)** in JAGS, both assuming a Bernoulli likelihood for the binary outcome.

1.  **Logistic Regression:** Utilized a logit link function to model the probability of high usage.
2.  **Probit Regression:** Utilized a probit link function for the same purpose.

Both models were built with **uninformative normal priors** to ensure the results were driven by the data. Convergence was successfully confirmed for both models using Trace Plots, the Gelman-Rubin diagnostic ($\hat{R} = 1.00$), and high Effective Sample Sizes (ESS).

---

### 📈 Results & Model Choice
Model performance was compared using the Deviance Information Criterion (DIC) and the Watanabe-Akaike Information Criterion (WAIC). The **Probit Regression model was selected** as the better choice because its lower DIC and WAIC values indicate a superior balance of model fit and complexity.

---

### 🏆 Conclusion
The **Probit Regression model** proved to be a slightly better and more reliable classifier for predicting mobile user behavior in this analysis. It successfully identified key predictors like `Screen On Time` and `Device Model`. While the model is effective, further refinement could enhance its predictive accuracy.

### 🖋 Author
Aquila Kyne Sudiro
Caroline Ang
Laurel Evelina Widjaja
