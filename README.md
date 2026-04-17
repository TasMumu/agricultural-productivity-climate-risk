
# Climate Risk and Agricultural Productivity in Asia

### A Cross-Country Integrated Data Engineering and Spatial Analysis Study

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Data](https://img.shields.io/badge/Data-FAOSTAT%20%7C%20NASA%20POWER-green)
![Model](https://img.shields.io/badge/Model-OLS%20%7C%20Random%20Forest-orange)
![Spatial](https://img.shields.io/badge/Spatial-Moran's%20I-purple)
![License](https://img.shields.io/badge/Data-Open%20Access-lightgrey)

---

**Period:** 2010–2024
**Geographic Scope:** 24 Asian Nations

**Author:** Tasnim Ahmad Mumu
Data Analyst | Climate Data Science & Agricultural Systems

---

## Abstract

This study investigates the extent to which climate variability explains agricultural productivity across 24 Asian countries over the period 2010–2024, using an integrated, multi-source dataset. Agricultural indicators—including crop yield and production—are sourced from FAOSTAT, while temperature and precipitation data are derived from the NASA POWER API using multi-point spatial sampling (3–5 coordinates per country).

A composite Climate Risk Score is constructed from min-max normalised temperature and rainfall indicators and classified into low, medium, and high stress categories.

Across all model specifications—OLS regression, polynomial regression, Random Forest, and exploratory spatial analysis—results indicate weak and statistically insignificant relationships between climate variables and yield outcomes. Increasing model complexity does not improve predictive performance, with consistently low explanatory power and negative cross-validated R² values.

Moran’s I spatial analysis reveals modest but statistically significant clustering of climate risk, yet these spatial patterns do not translate into consistent agricultural outcomes.

**Key finding:** Climate variables alone are insufficient to explain cross-country variation in agricultural productivity.

---

## Results Visualization

### Climate Risk vs Yield

![Risk vs Yield](outputs/figures/fig1_risk_vs_yield.png)

* Weak negative relationship
* High dispersion across countries
* Limited explanatory power

---

### Temperature & Rainfall Effects

![Temp Rain Yield](outputs/figures/fig2_temp_rain_vs_yield.png)

* Temperature impact varies by region
* Rainfall shows non-linear behavior
* Indicates complex climate–yield dynamics

---

### Scenario-Based Yield Projection

![Scenario Projection](outputs/figures/fig3_scenario_projection.png)

* Yield declines under increasing risk
* Prediction intervals widen under stress
* Highlights uncertainty in extreme scenarios

---

### Climate Risk Distribution

![Risk Distribution](outputs/figures/fig4_risk_distribution.png)

* Majority in medium-risk range
* High-risk countries drive variability

---

## 1. Research Context and Objectives

### Background

Agriculture in Asia is highly vulnerable to climate variability, with rising temperatures and shifting precipitation patterns affecting productivity across regions.

### Objectives

* Evaluate climate risk–yield relationship
* Compare model performance (OLS, RF)
* Conduct spatial analysis (Moran’s I)
* Develop policy-relevant classification

---

## 2. Data Architecture

### Data Sources

| Dataset    | Source         | Years     |
| ---------- | -------------- | --------- |
| Crop Data  | FAOSTAT        | 2010–2024 |
| Population | FAOSTAT        | 2010–2024 |
| Climate    | NASA POWER API | 2010–2024 |
| Geography  | Natural Earth  | —         |

---

### Data Model

| Dimension  | Variable    | Role         |
| ---------- | ----------- | ------------ |
| Yield      | hg/ha       | Productivity |
| Production | tonnes      | Capacity     |
| Climate    | Temp, Rain  | Stress       |
| Risk       | Score (0–1) | Composite    |
| Population | Count       | Context      |

---

## 3. Climate Risk Model

```math id="r1d9lc"
Risk = w_1 \cdot Temp_{norm} + w_2 \cdot (1 - Rain_{norm})
```

---

## 4. Methodology

### Pipeline

1. Data acquisition
2. Data preprocessing
3. Integration
4. Feature engineering
5. Modeling
6. Visualization

---

### Methods

| Method              | Purpose               |
| ------------------- | --------------------- |
| OLS                 | Baseline relationship |
| Random Forest       | Prediction            |
| Polynomial Regression       | Prediction            |
| Pearson Correlation | Association           |
| Moran’s I           | Spatial clustering    |
| K-means             | Grouping              |

---

## 5. Key Findings

* Climate variables show **weak explanatory power**
* Model performance remains **consistently low**
* Spatial clustering exists but **does not translate to yield patterns**
* Structural factors dominate agricultural productivity

---

## 6. Limitations

* Aggregation bias
* Missing structural variables
* No causal inference
* Small sample size

---

## 7. Reproducibility

### Requirements

```bash id="lf53dl"
python >= 3.9
pip install pandas numpy scipy matplotlib requests geopandas scikit-learn
```

---

### Run

```bash id="oqxh2u"
git clone https://github.com/your-username/climate-risk-agriculture.git
cd climate-risk-agriculture
pip install -r requirements.txt
jupyter notebook
```

---

## 8. Project Structure

```id="6ys1n9"
climate-risk-agriculture/
├── data/
├── notebooks/
├── scripts/
├── outputs/
│   └── figures/
├── requirements.txt
└── README.md
```

---

## 9. Future Work

* Panel data models
* Sub-national analysis
* Structural variables
* GIS modeling
* Causal inference

---


## Author

**Tasnim Ahmad Mumu**
Data Engineer | Climate Data Science · Agricultural Systems

---

## Final Note

**Open Data · Reproducible Research · Climate Analytics**

---

