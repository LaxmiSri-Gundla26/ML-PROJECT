# Climate Pattern Analysis Using K-Means Clustering and PCA

An end-to-end data science project that analyzes regional climate patterns across Indian cities using **Principal Component Analysis (PCA)** for dimensionality reduction and **K-Means Clustering** to segment weather profiles.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Dataset Information](#dataset-information)
- [Project Pipeline](#project-pipeline)
- [Key Features Analyzed](#key-features-analyzed)
- [Methodology & Evaluation](#methodology--evaluation)
- [Results & Key Findings](#results--key-findings)
- [Technologies Used](#technologies-used)
- [How to Run](#how-to-run)

---

## 📖 Overview
Climate datasets contain highly correlated, multi-dimensional environmental variables (temperature, humidity, air quality, pressure, etc.). This project applies unsupervised machine learning to:
1. Reduce dimensionality while preserving core variance using **PCA**.
2. Identify distinct climate patterns across regions using **K-Means Clustering**.
3. Evaluate optimal cluster structures using **Silhouette Analysis** and the **Elbow Method**.

---

## 📊 Dataset Information
* **Dataset**: Indian Climate Dataset (2024–2025)
* **Source**: Downloaded automatically via `kagglehub` (`ankushnarwade/indian-climate-dataset-20242025`)
* **Size**: 7,310 entries across 13 columns
* **Coverage**: Daily weather observations across major Indian cities (e.g., Mumbai, Delhi, Bengaluru, Chennai, Kolkata)

---

## 🛠️ Project Pipeline
1. **Data Ingestion**: Downloaded directly via `kagglehub` and loaded into Pandas.
2. **Data Cleaning**: Checked and handled duplicates and missing values (`dropna`, `drop_duplicates`).
3. **Exploratory Data Analysis**: Visualized feature correlation heatmaps across numerical variables.
4. **Feature Scaling**: Standardized numerical features using `StandardScaler`.
5. **Dimensionality Reduction**: Reduced 9 numerical climate features into **2 Principal Components** using PCA.
6. **Clustering & Evaluation**: Evaluated $K=2$ to $K=6$ clusters using Silhouette Scores and selected $K=3$ for domain interpretation.
7. **Export**: Exported cluster assignments to `climate_pattern_analysis_results.csv`.

---

## 🔬 Key Features Analyzed
- `Temperature_Max (°C)`, `Temperature_Min (°C)`, `Temperature_Avg (°C)`
- `Humidity (%)`
- `Rainfall (mm)`
- `Wind_Speed (km/h)`
- `AQI` (Air Quality Index)
- `Pressure (hPa)`
- `Cloud_Cover (%)`

---

## 📈 Methodology & Evaluation

### Principal Component Analysis (PCA)
- Reduced **9 numerical features** to **2 components**.
- **Explained Variance Ratio**: 
  - PC1: `32.18%`
  - PC2: `11.50%`
  - Total Explained Variance: `~43.68%`

### Silhouette Analysis ($K$-Selection)
- **$K = 2$**: Silhouette Score = `0.4532`
- **$K = 3$**: Silhouette Score = `0.3364` *(Selected for interpretability)*
- **$K = 4$**: Silhouette Score = `0.3549`
- **$K = 5$**: Silhouette Score = `0.3417`
- **$K = 6$**: Silhouette Score = `0.3339`

---

## 💡 Results & Key Findings

The clusters capture distinct temperature profiles across regions:

| Cluster | Assigned Label | Avg Temp (°C) | Max Temp (°C) | Min Temp (°C) | Humidity (%) | AQI |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **0** | Cool / Low Temp | ~23.1°C | ~28.4°C | ~17.8°C | ~62.9% | ~191.4 |
| **1** | Extreme / Hot | ~36.9°C | ~41.6°C | ~32.2°C | ~63.2% | ~194.5 |
| **2** | Moderate | ~30.0°C | ~34.9°C | ~25.0°C | ~61.9% | ~195.3 |

---

## 💻 Technologies Used
* **Python 3.x**
* **Data Processing**: `pandas`, `numpy`
* **Machine Learning**: `scikit-learn` (`StandardScaler`, `PCA`, `KMeans`, `silhouette_score`)
* **Visualization**: `matplotlib`, `seaborn`
* **Data Download**: `kagglehub`

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
   cd your-repository-name
