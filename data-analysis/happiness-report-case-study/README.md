# World Happiness Report Analysis & Machine Learning

> ## Educational Project: 
> This project is an educational reproduction of a case study developed by USP (University of São Paulo) students. It is intended exclusively for learning, self-study, and portfolio demonstration. All credit for the original study design and analysis belongs to the original USP research team.
> The project presented here is an educational and portfolio-oriented reproduction of the original study, created for technical learning and demonstration purposes.

> Source: ICMC — https://www.icmc.usp.br/noticias/6869-trabalho-da-usp-analisa-aspectos-que-impactam-a-felicidade-ao-redor-do-mundo


## 📌 Project Overview
This repository contains a comprehensive study on global happiness levels using the **World Happiness Report (2005–2023)** dataset from Kaggle. 

The main objective is to analyze regional happiness trends, evaluate the impact of the **COVID-19 pandemic** on global well-being, and build predictive machine learning models to identify the key socioeconomic and emotional drivers of happiness.

---

## 🎯 Objectives
* **Trend & Regional Analysis:** Evaluate the happiness index (`Ladder Score`) across different countries and regions over time.
* **COVID-19 Impact Study:** Compare pre-pandemic (2018–2019) and post-pandemic (2020–2021) metrics to assess changes in well-being and economic indicators.
* **Predictive Modeling:** Train and evaluate Regression models to predict global happiness scores based on social, economic, and emotional attributes.

---

## 📊 Dataset & Features
The study utilizes historical data with 2,363 entries and 12 main attributes:

* **Country name:** Name of the country (Categorical)
* **Year:** Year of observation (2005–2023)
* **Regional indicator:** Geographical region
* **Ladder score:** Self-reported happiness score based on the Cantril Ladder (0 to 10 scale)
* **Log GDP per capita:** Natural log of GDP per capita adjusted for Purchasing Power Parity (PPP)
* **Social support:** National average of binary responses on having support in times of need
* **Healthy life expectancy:** Average number of years a newborn would live in good health
* **Freedom to make life choices:** Satisfaction with freedom of choice in life
* **Generosity:** Measure of charitable donations adjusted for GDP
* **Perceptions of corruption:** National average regarding perceived corruption in government and business
* **Positive affect:** Average of positive emotions experienced the day prior
* **Negative affect:** Average of negative emotions experienced the day prior

---

## ⚙️ Data Preprocessing & Feature Engineering

1. **Handling Missing Values & Outliers:**
   * Address missing numerical data (332 null entries across attributes).
   * Boxplot analysis revealed substantial outliers; robust scaling techniques were evaluated.

2. **Data Normalization:**
   * Applied `MinMaxScaler` to numerical features, standardizing values to the $[0, 1]$ interval to enhance distance-based models like KNN.

3. **Feature Engineering (Pandemic Impact Analysis):**
   * **Pre-Pandemic Baseline:** $\text{LifeLadder}_{\text{Pre-Pandemic}} = \frac{\text{LadderScore}_{2018} + \text{LadderScore}_{2019}}{2}$
   * **Post-Pandemic Score:** $\text{LifeLadder}_{\text{Post-Pandemic}} = \frac{\text{LadderScore}_{2020} + \text{LadderScore}_{2021}}{2}$
   * **Delta Calculation:** $\Delta_{\text{LadderScore}} = \text{LadderScore}_{\text{Post-Pandemic}} - \text{LadderScore}_{\text{Pre-Pandemic}}$
     * $\Delta > 0$: Increased happiness post-pandemic.
     * $\Delta < 0$: Decreased happiness post-pandemic.

---

## 🔍 Key Findings

* **Economic Growth vs. Happiness Change ($\Delta_{\text{GDP}} = -0.01$):** 
  * Near-zero correlation between changes in GDP per capita and changes in happiness during the pandemic period, suggesting economic growth alone did not buffer well-being during global crises.
* **Social Support ($\text{Correlation} = +0.30$):** 
  * A positive correlation indicates that strong social safety nets and interpersonal support played a vital role in countries that maintained or improved happiness levels during COVID-19.
* **Negative Affect ($\text{Correlation} = -0.38$):** 
  * A negative correlation highlights how short-term emotional distress and negative experiences directly coincided with a drop in overall happiness ratings.

---

## 🤖 Machine Learning & Modeling

Predictive models were built to estimate the `Ladder Score` using key socioeconomic and emotional features:

* **Algorithms Evaluated:** Linear Regression and Random Forest Regressor.
* **Evaluation Metrics:**
  * Coefficient of Determination ($R^2$)
  * Mean Absolute Error ($\text{MAE}$)
  * Root Mean Squared Error ($\text{RMSE}$)

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`
* **Machine Learning & Preprocessing:** `scikit-learn`

---

## Conclusions and Insights

The analysis shows that happiness is shaped by a combination of economic, social, and emotional factors, rather than by income alone. Although GDP per capita remains an important component of well-being, the results suggest that changes in economic output during the pandemic were not strongly associated with changes in happiness, indicating that financial conditions alone are not sufficient to explain variations in life satisfaction.

The strongest and most consistent signal was the role of social support. Countries with stronger support networks tended to maintain or improve their happiness levels during the pandemic, suggesting that interpersonal trust, community resilience, and emotional safety are essential buffers in times of crisis. In contrast, negative affect showed a clear inverse relationship with happiness: higher levels of distress, stress, and negative emotional experiences were associated with lower life satisfaction.

The regional analysis reinforces the idea that the distribution of happiness is uneven across the world. Countries in Europe, North America, and parts of Oceania consistently show higher average happiness scores, while many countries in Africa and South Asia remain at the lower end of the scale. This pattern points to structural inequalities in health, social protection, political stability, and access to basic resources, which directly affect overall life satisfaction.

Regarding the period before and after COVID-19, the study suggests that the pandemic had a differentiated impact across countries. Some nations became happier or recovered quickly, while others experienced marked declines. This heterogeneity indicates that each country's resilience depended on its institutional capacity, social support systems, and how effectively it managed health and economic disruption.

From a modeling perspective, the predictive analysis confirms that happiness is not driven by a single attribute. The best-performing models were able to explain a meaningful portion of variation in the Ladder Score using socioeconomic and emotional variables, reinforcing the idea that well-being is a multidimensional outcome. Among the most relevant predictors, social support, health, and personal freedom emerged as particularly important, while negative emotional states had a detrimental effect on the final score.

Overall, the study indicates that well-being is best understood as a multidimensional concept: economic development matters, but it is not enough on its own. Social cohesion, emotional health, freedom, public trust, and institutional stability are central to building sustainable happiness across countries and over time.


## References
- Helliwell, J. F., Layard, R., Sachs, J. D., De Neve, J.-E., Aknin, L. B., & Wang, S. (Eds.). World Happiness Report. Sustainable Development Solutions Network (SDSN).

- Gallup World Poll. Data and methodology for global well-being and life evaluation metrics. Gallup, Inc.

- Kaggle Dataset: World Happiness Report Data. Available on Kaggle.

- Molnar, C. (2022). Interpretable Machine Learning: A Guide for Making Black Box Models Explainable. christophm.github.io/interpretable-ml-book

- McKinney, W. (2010). Data Structures for Statistical Computing in Python. Proceedings of the 9th Python in Science Conference, 56–61.

## Source and Original Publication

This analysis is based on a study originally published by the University of São Paulo's ICMC (Institute of Mathematical and Computer Sciences), and it was also featured in the Infogeral portal and in the Jornal da USP. The original article can be accessed here:

- ICMC: https://www.icmc.usp.br/noticias/6869-trabalho-da-usp-analisa-aspectos-que-impactam-a-felicidade-ao-redor-do-mundo

## ▶️ How to Run

### 1. Open the analysis folder
```bash
cd data-analysis/happiness-report-case-study
```

### 2. Create and activate a virtual environment

On Windows:
```bash
python -m venv .venv
.venv\Scripts\activate
```

On macOS/Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Open the notebook
```bash
jupyter notebook happiness-report-case-study.ipynb
```

or open the file directly in VS Code and select the project virtual environment as the Python kernel.

### 5. Run the notebook
Use the notebook interface to execute cells sequentially, or choose:
- `Run All`
- `Restart and Run All`

### 6. Optional: install extra notebook dependency
If the notebook shows a missing package error, install it in the same environment:

```bash
pip install plotly
```

---