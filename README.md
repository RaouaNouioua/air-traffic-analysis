✈️ Air Traffic Pattern Analysis — Data Mining Project

Operational pattern discovery in Algerian airport flight data using K-Means Clustering and Apriori Association Rules.

Author: Raoua Nouioua
Date: February 2026
Dataset: 157,672 flight records

📌 Project Overview
This project applies data mining techniques to analyze flight operations data at Algerian airports, uncovering hidden patterns to provide actionable insights for optimizing air traffic management.
Key questions answered:

Which flights always fail? (specific times & routes with systemic issues)
Which operations work perfectly?
How to schedule smarter using data-driven rules?


🗂️ Project Structure
air-traffic-analysis/
│
├── Complete_Project_data_mining.ipynb   # Main notebook (all 6 phases)
├── data_mining_report.pdf               # Full written report
├── Air_Traffic_Analysis_Enhanced.pptx  # Presentation slides
└── README.md

🔬 Methodology
The project follows a structured 6-phase pipeline:
PhaseDescription1Business Understanding2Data Understanding & Exploration3Data Preparation & Feature Engineering4Exploratory Data Analysis (EDA)5K-Means Clustering (k=8)6Apriori Association Rule Mining
Feature Engineering (12 custom features)

Temporal: hour, day_of_week, month, year, is_weekend
Business: time_period, is_peak, status_category
Operational: is_domestic, airline_category, is_delayed, is_cancelled


📊 Key Results
Clustering (K-Means, k=8 — Silhouette Score: 0.302)
ClusterDescriptionSizePerformanceC2Weekend operations26.6%✅ 0% issuesC6Domestic reliability13.6%✅ 0% issuesC0Afternoon Paris routes (3:06 PM)15.7%✅ 0% issuesC7Evening peak (5:00 PM)14.0%✅ 0% issuesC3Evening delays (4:30 PM)3.6%❌ 100% delayedC4Afternoon cancellations (1:30 PM)2.2%❌ 100% cancelled
Association Rules (Apriori)
RuleConfidence{Domestic, Morning} → {Major, OffPeak, Normal_Operation}81.6%{Night, Normal_Operation} → {International, OffPeak}90.5%{Night, International, Normal_Operation} → {OffPeak}100%
Critical Discovery: Real Peak Hours
Standard assumption (7–9 AM) is wrong for Algerian airports.
Data-derived peak hours: 10:00 AM and 15:00–18:00.

⚙️ Setup & Installation
Requirements
bashpip install pandas numpy matplotlib seaborn scikit-learn mlxtend
Dependencies Summary
LibraryVersionUsagepandas≥1.3Data loading & manipulationnumpy≥1.21Numerical operationsmatplotlib≥3.4Visualizationsseaborn≥0.11Statistical plotsscikit-learn≥0.24K-Means, StandardScaler, LabelEncodermlxtend≥0.19Apriori & association rules
Running the Notebook

Clone the repository:

bash   git clone https://github.com/your-username/air-traffic-analysis.git
   cd air-traffic-analysis

Install dependencies:

bash   pip install -r requirements.txt

Open the notebook:

bash   jupyter notebook Complete_Project_data_mining.ipynb
Or open directly in Google Colab (recommended — the notebook was developed there).

⚠️ The notebook expects a flight dataset to be loaded in Phase 2. Update the data loading cell with your file path or Kaggle/Drive link accordingly.


📈 Business Impact
AreaExpected ImprovementOn-time performance10–15% improvementResource optimisationBetter staff & gate allocationRevenue opportunitiesExpand successful time slots & routesCustomer satisfactionReduced delays and cancellations

🧠 Technologies Used

Python (Google Colab environment)
scikit-learn — K-Means clustering
mlxtend — Apriori frequent itemset mining
pandas / numpy — Data wrangling
matplotlib / seaborn — Visualisation


📄 License
This project was developed as part of an academic Data Mining course at ENSIA (École Nationale Supérieure d'Informatique), Algeria.