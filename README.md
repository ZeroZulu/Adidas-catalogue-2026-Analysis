<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,50:FF6B35,100:1a1a2e&height=200&section=header&text=Adidas%20Global%20Catalogue%202026&fontSize=36&fontColor=ffffff&fontAlignY=38&desc=End-to-End%20Data%20Analysis%20%7C%2010%20Chapters%20%7C%2044%2C888%20SKUs&descAlignY=58&descSize=16&descColor=FF6B35" />

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Plotly](https://img.shields.io/badge/Plotly-Interactive-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)](https://plotly.com)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://kaggle.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

<br/>

**44,888 SKUs · 10 Countries · 19 Visualisations · 5 Interactive Charts · 4-Model ML · NLP Recommender**

</div>

---

## 📌 Overview

A comprehensive end-to-end data analysis of the **Adidas Global Catalogue 2026** dataset, covering 10 countries, 44,888 SKUs, and spanning the full data science lifecycle from cleaning through machine learning and strategic recommendations.

Built with a full **Adidas brand design system** — custom colour palette, HTML chapter banners, and consistent chart styling throughout.

| Metric | Value |
|--------|-------|
| 🗂️ **Total SKUs** | 44,888 |
| 🌍 **Countries** | 10 (US, GB, DE, FR, JP, KR, CN, IN, MX, BR) |
| 📦 **Product Categories** | 12 normalised (from 53 multilingual raw variants) |
| 💰 **Median Price** | ~$107 USD (FX-converted) |
| ⭐ **Avg Rating** | 4.67 / 5.0 |
| 📊 **Charts** | 19 matplotlib + 5 interactive Plotly |
| 🤖 **ML Models** | 4 (Linear, Ridge, Random Forest, Gradient Boosting) |

---

## 🗂️ Project Structure

```
adidas-global-catalogue-2026/
│
├── adidas-catalogue-2026-analysis.ipynb   ← Main notebook (46 cells)
├── README.md
│
└── /kaggle/working/                       ← Auto-generated on run
    ├── adidas_global_2026_product_level.csv   (one row per product × country)
    └── adidas_global_2026_sku_level.csv       (one row per product × country × size)
```

---

## 📖 Chapters

| # | Chapter | Highlights |
|---|---------|------------|
| 1 | **Setup & Data Loading** | Load all 10 country CSVs · FX normalisation (Q1 2026 rates) · Multilingual category mapping · Gender normalisation |
| 2 | **Data Quality Assessment** | Missing value heatmap · Duplicate detection · Product-level aggregation · Outlier detection |
| 3 | **Exploratory Data Analysis** | Categorical distributions · Price violin/KDE by category · Correlation matrix · Pair plot |
| 4 | **Product Portfolio Deep-Dive** | Interactive sunburst (category → gender) · Gender × Category heatmap · Country comparison bars · Colour trend analysis |
| 5 | **Pricing Strategy** | Price tier segmentation (Budget/Mid/Premium/Luxury) · Country comparison · Discount depth analysis · Price elasticity simulation |
| 6 | **Availability & Market Reach** | Stock status donut · Availability stacked bars by country · Multi-market product reach scatter |
| 7 | **Rating & Review Intelligence** | Rating distribution · Avg rating by category · Rating vs price · Top-rated products table |
| 8 | **NLP: Mining Product Names** | Word frequency · Word cloud · TF-IDF keywords by category · **Content-based recommender engine** |
| 9 | **Machine Learning** | K-Means clustering (elbow + silhouette) · PCA 2D projection · **4-model price prediction** · Feature importance · Segment positioning map |
| 10 | **Business Insights** | KPI dashboard · Key findings · **Strategic recommendations table** |

---

## 🤖 Machine Learning

### Price Prediction (Chapter 9.3)

Four models trained and cross-validated on product-level features:

| Model | Features |
|-------|----------|
| Linear Regression | Baseline |
| Ridge Regression | L2 regularisation |
| Random Forest | 200 estimators, `n_jobs=-1` |
| **HistGradient Boosting** | **Best R² — 10× faster than vanilla GBR** |

Features: `category`, `gender`, `country` (encoded) + `rating`, `discount_pct`, `size_count`, `seen_market_count`  
CV strategy: random-sampled 5,000-row subset for representative cross-validation scores

### Clustering (Chapter 9.1–9.2)

K-Means with elbow + silhouette selection across k=2–9. PCA 2D projection with Plotly interactive scatter. Four identified archetypes:

- 🟠 **Premium Multi-Market** — high price, broad availability
- 🟡 **Budget Single-Market** — low price, local focus
- 🔵 **Active Performance** — mid-price, high review count
- 🟢 **Lifestyle Entry** — mass-market lifestyle products

---

## 📊 Key Findings

| Finding | Detail |
|---------|--------|
| 💰 **Price gap** | US median ~$73 vs EU median ~$121–131 — largest cross-market spread |
| 🏃 **Catalogue concentration** | Lifestyle + Running = 60%+ of SKUs — over-concentration risk |
| 🌏 **Market reach** | India stocks most unique products; China stocks fewest |
| 👗 **Gender gap** | Men's products outnumber Women's 1.5:1 — underserved segment |
| ⭐ **Rating ceiling** | Avg 4.67 with tight distribution — limited differentiation signal |
| 📈 **Multi-market premium** | Products in 8+ markets command rating and price premiums |
| 🏷️ **Discount concentration** | Only ~14% of products on sale; heaviest in MX and BR |

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| **Data** | pandas · numpy |
| **Visualisation** | matplotlib · seaborn · plotly express · plotly graph objects |
| **NLP** | NLTK · TF-IDF (scikit-learn) · WordCloud · cosine similarity |
| **ML** | scikit-learn (KMeans, PCA, RandomForest, HistGradientBoosting, Ridge) |
| **Design** | Custom Adidas brand system · HTML/CSS chapter banners |

---

## 🚀 How to Run

### On Kaggle (Recommended)

1. Open [the notebook on Kaggle](https://www.kaggle.com/)
2. Add dataset: **Data → Add Data → search "Adidas Global Catalogue 2026" by bsthere**
3. Click **Run All**

### Locally

```bash
# Clone
git clone https://github.com/YOUR_USERNAME/adidas-global-catalogue-2026.git
cd adidas-global-catalogue-2026

# Install dependencies
pip install -r requirements.txt

# Launch
jupyter notebook adidas-catalogue-2026-analysis.ipynb
```

---

## 📦 Requirements

```txt
pandas>=2.0
numpy>=1.24
matplotlib>=3.7
seaborn>=0.12
plotly>=5.14
scikit-learn>=1.3
nltk>=3.8
wordcloud>=1.9
jupyter>=1.0
```

---

## 📁 Outputs

Two clean CSV files are exported at the end of the notebook:

| File | Description | Granularity |
|------|-------------|-------------|
| `adidas_global_2026_product_level.csv` | One row per product × country. Used for most analyses. | ~18,000 rows |
| `adidas_global_2026_sku_level.csv` | Full dataset with all size variants. | 44,888 rows |

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:FF6B35,100:000000&height=100&section=footer" />
</div>
