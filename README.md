
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

### Top Countries by Production in 2024
![Top Countries by production](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/58825436a8422ce0ed5e269091afcb6adb1b0ec8/Visualizations/Top%20Countries%20by%20production.png)

* China dominates production (**873.94 million tons**)
* India is a distant second (**525.30 million tons**)
* Indonesia follows at **331.06 million tons**


### Climate Risk vs Yield

![Risk vs Yield](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/58825436a8422ce0ed5e269091afcb6adb1b0ec8/Visualizations/climate%20risk%20vs%20yield.png)

* Crop response to climate risk is heterogeneous: root crops show increasing yields under higher risk, while vegetables exhibit slight sensitivity, and staple crops (cereals, pulses) remain relatively stable.
---

### Country level Production vs Climate Risk

![Country level Production vs Climate Risk](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/58825436a8422ce0ed5e269091afcb6adb1b0ec8/Visualizations/Country%20level%20Production%20vs%20Climate%20Risk.png)

Slight positive relationship between climate risk and production.
High-production countries like China (873.94) and India (525.30) operate under moderate–high risk levels

**Insight:**
Large agricultural economies absorb climate stress through scale and resilience.
Climate risk alone does not significantly reduce total production output

---

### Production per capita vs Country

![Production per capita vs country](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/58825436a8422ce0ed5e269091afcb6adb1b0ec8/Visualizations/Production%20per%20capita%20vs%20country.png)

* Malaysia leads with the highest production per person (490), followed by Thailand (380) and Kazakhstan (210)
* Mid-tier countries include Turkey, Indonesia, and China (150–200 range)
* Large population countries like India (110) and Bangladesh (70) show lower per capita output

---

### Food Availability vs Climate Risk
![food availability vs climate ris](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/58825436a8422ce0ed5e269091afcb6adb1b0ec8/Visualizations/food%20availability%20vs%20climate%20ris.png)

* Weak or no clear relationship between climate risk and food availability
* Some high-risk countries (e.g., Oman, Saudi Arabia) maintain moderate availability, while some low-risk countries show lower output

---

### Risk vs Outcomes
![risk vs outcomes](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/58825436a8422ce0ed5e269091afcb6adb1b0ec8/Visualizations/risk%20vs%20outcomes.png)

* Weak or no clear relationship between climate risk and food availability
* Some high-risk countries (e.g., Oman, Saudi Arabia) maintain moderate availability, while some low-risk countries show lower output

---

### OLS Regression
![OLS Regression](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/6299a9d1c8bdd4444ced62c00cd76a2db97b68fa/Visualizations/ols.png)

---

### Random Forest
![Random Forest](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/6299a9d1c8bdd4444ced62c00cd76a2db97b68fa/Visualizations/random%20forest.png)

---

### Polynomial Regression
![Polynomial Regression](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/6299a9d1c8bdd4444ced62c00cd76a2db97b68fa/Visualizations/poly%201.png)

![Polynomial Regression](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/6299a9d1c8bdd4444ced62c00cd76a2db97b68fa/Visualizations/poly%202.png)

---

### Spatial Distribution
![Spatial Distribution](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/44ebbf979ffe7b0270ea729525f7952fe5871b1b/Visualizations/spatial%20distribution.png)

**Spatial Interpretation**

Climate risk and food availability do not show a clear inverse spatial pattern across Asia. Several high-risk regions (e.g., Southeast Asia) maintain relatively high per capita production, while some lower-risk areas exhibit moderate or low availability.

---

### Crop Group Heatmap
![crop group heatmap](https://github.com/TasMumu/agricultural-productivity-climate-risk/blob/44ebbf979ffe7b0270ea729525f7952fe5871b1b/Visualizations/crop%20group%20heatmap.png)

Top countries by total production:
'China', 'India', 'Indonesia', 'Thailand', 'Pakistan', 'Turkey', 'Vietnam', 'Malaysia', 'Bangladesh', 'Philippines'


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


