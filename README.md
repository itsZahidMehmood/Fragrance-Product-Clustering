# Fragrance Product Clustering | Unsupervised Machine Learning

An end-to-end machine learning project that applies unsupervised learning techniques to segment an e-commerce fragrance catalogue into meaningful product groups based on price, sales performance, and inventory position.

The project compares multiple clustering algorithms, evaluates their performance and stability, and translates the resulting product segments into actionable business recommendations.

## Project Overview

The dataset contains approximately 1,000 fragrance product listings with information about prices, units sold, availability, product categories, brands, and shipping locations.

Since the dataset does not contain predefined product-segment labels, unsupervised machine learning was used to discover groups of products with similar commercial characteristics.

After data cleaning and experimentation, **K-Means with six clusters** was selected as the final segmentation model.

## Objectives

- Explore and audit product listing data.
- Handle missing values, inconsistent categories, and mixed currencies.
- Apply feature engineering and log transformations.
- Compare different clustering algorithms.
- Evaluate clustering quality and stability.
- Use Principal Component Analysis (PCA) to visualise cluster structure.
- Identify commercially meaningful product segments.
- Develop inventory, pricing, and merchandising recommendations.

## Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- SciPy
- Matplotlib
- Seaborn
- PCA
- K-Means Clustering
- Agglomerative Hierarchical Clustering
- DBSCAN
- Gaussian Mixture Models

## Machine Learning Workflow

1. **Data Auditing:** Examined missing values, duplicate records, inconsistent product categories, and data-quality issues.
2. **Data Cleaning:** Recovered selected missing values, standardised currencies, and converted availability into ordinal stock bands.
3. **Feature Engineering:** Created log-transformed price and sales features.
4. **Feature Selection:** Selected log price, log units sold, and stock band as the core clustering variables.
5. **Clustering:** Implemented and compared four unsupervised learning algorithms.
6. **Model Evaluation:** Used Silhouette Score, Davies–Bouldin Index, Calinski–Harabasz Score, and bootstrap stability.
7. **Dimensionality Reduction:** Applied PCA to visualise the clustering solutions.
8. **Business Interpretation:** Analysed cluster profiles and developed inventory and merchandising recommendations.

## Models Compared

| Algorithm | Result |
|---|---|
| K-Means | Selected final model (6 clusters) |
| Agglomerative Clustering | Ward linkage |
| DBSCAN | Density-based clustering |
| Gaussian Mixture Model | Probabilistic clustering |

## Key Results

The final K-Means model identified six product segments across 994 cleaned product records.

| Evaluation Metric | Result |
|---|---:|
| Number of clusters | 6 |
| Silhouette Score | 0.309 |
| Davies–Bouldin Index | 0.988 |
| Calinski–Harabasz Score | 447.7 |
| Bootstrap stability (ARI) | 0.95 ± 0.05 |
| Products retained after cleaning | 994 (99.4%) |

### Identified Product Segments

1. Bestsellers at Stock-Out Risk
2. Well-Stocked Bestsellers
3. Well-Stocked Premium
4. Low-Stock Premium
5. Overstocked Budget Lines
6. Low-Stock Slow Sellers

### Important Business Findings

- The 10% of products classified as bestsellers at stock-out risk account for 58.4% of the revenue proxy.
- 80% of this segment showed last-unit or low-stock indicators.
- Well-stocked bestsellers contribute another 32.6% of the revenue proxy.
- Overstocked budget products represent 19% of the catalogue but contribute only 0.6% of the revenue proxy.
- The six segments provide different opportunities for replenishment, pricing, and product-range management.

*Revenue figures represent price multiplied by cumulative units sold, not actual profit.*

## Model Evaluation

K-Means was selected because it achieved the strongest overall internal evaluation results among the four tested algorithms and demonstrated high bootstrap stability.

DBSCAN and Gaussian Mixture Models were also evaluated, but their results largely reflected the discrete stock-band variable rather than commercially meaningful product groupings.

## Visualisations

The analysis includes:

- Data quality audit
- Price and sales distributions before and after log transformation
- Product category and stock-band distributions
- Feature correlation heatmap
- Elbow, Silhouette, and Davies–Bouldin plots
- Hierarchical clustering dendrogram
- DBSCAN k-distance plot
- PCA scree plot and biplot
- Clustering model comparison
- Silhouette analysis
- Cluster assignment confidence
- Product segment profiles

## Project Structure

```text
fragrance-product-clustering/
│
├── ml_analysis.py
├── Sales-[5444].csv
├── requirements.txt
├── README.md
│
└── figs/
    ├── fig01_audit.png
    ├── fig02_dist.png
    ├── fig03_cats.png
    ├── fig04_corr.png
    ├── fig05_kmeans_k.png
    ├── fig06_dendrogram.png
    ├── fig07_kdist.png
    └── ...
```

The `figs/` directory is generated by the analysis script and contains the visualisations and result tables.

## Installation and Usage

### 1. Clone the repository

```bash
git clone https://github.com/itsZahidMehmood/fragrance-product-clustering.git
cd fragrance-product-clustering
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Add the dataset

Place the dataset file named `Sales-[5444].csv` in the project root directory.

### 4. Run the analysis

```bash
python ml_analysis.py
```

The script generates the analysis figures and result tables in the `figs/` directory.

## Requirements

```text
pandas
numpy
scipy
scikit-learn
matplotlib
seaborn
```

## Limitations

- The analysis uses a single May 2024 dataset snapshot.
- Units sold are cumulative and do not represent sales velocity.
- Stock availability is partly censored at ten units.
- Revenue is a gross merchandise value proxy; profit margins are unavailable.
- Some product assignments are borderline and should be reviewed before operational decisions.
## ScreenShots
<img width="530" height="433" alt="image" src="https://github.com/user-attachments/assets/03d9b72b-3447-41ab-9181-dc582cc5bca2" />
<img width="657" height="274" alt="image" src="https://github.com/user-attachments/assets/d37a76d2-e6c1-4ed8-8065-0cdcbad8f9f6" />
<img width="661" height="409" alt="image" src="https://github.com/user-attachments/assets/73420f87-3a83-41c0-a46f-ce6d930f527e" />



## Future Improvements

- Incorporate time-based sales data to calculate sales velocity.
- Use exact inventory quantities instead of censored stock bands.
- Explore mixed-type clustering methods such as K-Prototypes.
- Investigate HDBSCAN and consensus clustering.
- Validate recommendations using real business outcomes.

## Author

**Zahid Mehmood**

MSc Data Science | Machine Learning | Data Science | AI

- GitHub: https://github.com/itsZahidMehmood
- Portfolio: https://zahidinsights.com
- LinkedIn: https://www.linkedin.com/in/zahid-mehmood-389221220

---

*This project demonstrates practical experience in data preprocessing, feature engineering, unsupervised machine learning, model evaluation, dimensionality reduction, and business-focused data analysis.*
