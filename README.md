# Air Traffic Pattern Analysis — Data Mining Project

> Operational pattern discovery in Algerian airport flight data using K-Means Clustering and Apriori Association Rules

**Author:** Raoua Nouioua
**Date:** February 2026
**Dataset Size:** 157,672 flight records

---

## Project Overview

This project applies data mining techniques to analyze flight operations in Algerian airports and uncover hidden patterns that support data-driven decision making in air traffic management.

**Key Questions Addressed:**
- Which flights consistently fail? (specific routes & time periods with systemic issues)
- Which operations perform optimally?
- How can scheduling be improved using data-driven rules?

---

## Project Structure
```
air-traffic-analysis/
│
├── Air_Traffic_Analysis.ipynb   # Main notebook (all 6 phases)
├── Air_Traffic_Analysis.pdf     # Full written report
├── Air_Traffic_Analysis.pptx    # Presentation slides
└── README.md
```

---

## Methodology

The project follows a structured 6-phase data mining pipeline:

| Phase | Description |
|-------|-------------|
| 1 | Business Understanding |
| 2 | Data Understanding & Exploration |
| 3 | Data Preparation & Feature Engineering |
| 4 | Exploratory Data Analysis (EDA) |
| 5 | K-Means Clustering (k = 8) |
| 6 | Apriori Association Rule Mining |

### Feature Engineering

A total of 12 custom features were created:

**Temporal Features**
- `hour`, `day_of_week`, `month`, `year`, `is_weekend`

**Business Features**
- `time_period`, `is_peak`, `status_category`

**Operational Features**
- `is_domestic`, `airline_category`, `is_delayed`, `is_cancelled`

---

## Key Results

### 🔹 K-Means Clustering
- **k = 8** (determined by Elbow method)
- **Silhouette Score:** 0.302

| Cluster | Description | Size | Performance |
|---------|-------------|------|-------------|
| C2 | Weekend operations | 26.6% | 0% issues |
| C6 | Domestic reliability | 13.6% | 0% issues |
| C0 | Afternoon Paris routes (3:06 PM) | 15.7% | 0% issues |
| C7 | Evening peak (5:00 PM) | 14.0% | 0% issues |
| C3 | Evening delays (4:30 PM) | 3.6% | 100% delayed |
| C4 | Afternoon cancellations (1:30 PM) | 2.2% | 100% cancelled |

### 🔹 Association Rules (Apriori)

| Rule | Confidence |
|------|-----------|
| `{Domestic, Morning}` → `{Major, OffPeak, Normal_Operation}` | 81.6% |
| `{Night, Normal_Operation}` → `{International, OffPeak}` | 90.5% |
| `{Night, International, Normal_Operation}` → `{OffPeak}` | 100% |

**Data-Driven Peak Hours:** 10:00 AM and 15:00–18:00

---

## Setup & Installation

### Requirements
```bash
pip install requirements.txt
```

### Dependencies

| Library | Version | Usage |
|---------|---------|-------|
| `pandas` | ≥ 1.3 | Data manipulation |
| `numpy` | ≥ 1.21 | Numerical operations |
| `matplotlib` | ≥ 3.4 | Visualization |
| `seaborn` | ≥ 0.11 | Statistical plots |
| `scikit-learn` | ≥ 0.24 | K-Means & preprocessing |
| `mlxtend` | ≥ 0.19 | Apriori algorithm |

### Running the Project
```bash
git clone https://github.com/RaouaNouioua/air-traffic-analysis.git
cd air-traffic-analysis
pip install -r requirements.txt
jupyter notebook Air_Traffic_Analysis.ipynb
```

> You can also run the notebook on **Google Colab** (recommended).

---

## Dataset Notice

The dataset used in this project comes from Algerian airport  and is **not publicly available**.
Due to data privacy and permission restrictions, it is not included in this repository.

To run the notebook:
- Provide your own dataset, or
- Update the data loading step in Phase 2 with your file path

---

## Business Impact

| Area | Expected Improvement |
|------|---------------------|
| On-time performance | +10–15% |
| Resource optimization | Better staff & gate allocation |
| Revenue opportunities | Expand successful routes & time slots |
| Customer satisfaction | Reduced delays and cancellations |

---

##  Technologies Used

- **Python** (Google Colab environment)
- **scikit-learn** — K-Means clustering
- **mlxtend** — Apriori frequent itemset mining
- **pandas / numpy** — Data processing
- **matplotlib / seaborn** — Visualization

---

## License

This project was developed as part of a Data Mining course at **ENSIA** (École Nationale Supérieure d'Informatique) and this was my own contribution to that project , Algeria
