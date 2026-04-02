✈️ Air Traffic Pattern Analysis — Data Mining Project

Operational pattern discovery in Algerian airport flight data using K-Means Clustering and Apriori Association Rules

Author: Raoua Nouioua
Date: February 2026
Dataset Size: 157,672 flight records

📌 Project Overview
This project applies data mining techniques to analyze flight operations in Algerian airports and uncover hidden patterns that support data-driven decision making in air traffic management.
Key Questions Addressed:

Which flights consistently fail? (specific routes & time periods with systemic issues)
Which operations perform optimally?
How can scheduling be improved using data-driven rules?


🗂️ Project Structure
air-traffic-analysis/
│
├── Air_Traffic_Analysis.ipynb   # Main notebook (all 6 phases)
├── Air_Traffic_Analysis.pdf     # Full written report
├── Air_Traffic_Analysis.pptx    # Presentation slides
└── README.md

🔬 Methodology
The project follows a structured 6-phase data mining pipeline:
PhaseDescription1Business Understanding2Data Understanding & Exploration3Data Preparation & Feature Engineering4Exploratory Data Analysis (EDA)5K-Means Clustering (k = 8)6Apriori Association Rule Mining
Feature Engineering
A total of 12 custom features were created:
Temporal Features

hour, day_of_week, month, year, is_weekend

Business Features

time_period, is_peak, status_category

Operational Features

is_domestic, airline_category, is_delayed, is_cancelled


📊 Key Results
🔹 K-Means Clustering

k = 8 (determined by Elbow method)
Silhouette Score: 0.302

ClusterDescriptionSizePerformanceC2Weekend operations26.6%✅ 0% issuesC6Domestic reliability13.6%✅ 0% issuesC0Afternoon Paris routes (3:06 PM)15.7%✅ 0% issuesC7Evening peak (5:00 PM)14.0%✅ 0% issuesC3Evening delays (4:30 PM)3.6%❌ 100% delayedC4Afternoon cancellations (1:30 PM)2.2%❌ 100% cancelled
🔹 Association Rules (Apriori)
RuleConfidence{Domestic, Morning} → {Major, OffPeak, Normal_Operation}81.6%{Night, Normal_Operation} → {International, OffPeak}90.5%{Night, International, Normal_Operation} → {OffPeak}100%
🚨 Critical Insight

❗ The traditional assumption that peak hours are 7–9 AM is incorrect for Algerian airports.

✅ Data-Driven Peak Hours: 10:00 AM and 15:00–18:00

🛠️ Setup & Installation
Requirements
bashpip install pandas numpy matplotlib seaborn scikit-learn mlxtend
Dependencies
LibraryVersionUsagepandas≥ 1.3Data manipulationnumpy≥ 1.21Numerical operationsmatplotlib≥ 3.4Visualizationseaborn≥ 0.11Statistical plotsscikit-learn≥ 0.24K-Means & preprocessingmlxtend≥ 0.19Apriori algorithm
Running the Project
bashgit clone https://github.com/your-username/air-traffic-analysis.git
cd air-traffic-analysis
pip install -r requirements.txt
jupyter notebook Air_Traffic_Analysis.ipynb

💡 You can also run the notebook on Google Colab (recommended).


⚠️ Dataset Notice
The dataset used in this project comes from Algerian airport operations and is not publicly available.
Due to data privacy and permission restrictions, it is not included in this repository.
👉 To run the notebook:

Provide your own dataset, or
Update the data loading step in Phase 2 with your file path


📈 Business Impact
AreaExpected ImprovementOn-time performance+10–15%Resource optimizationBetter staff & gate allocationRevenue opportunitiesExpand successful routes & time slotsCustomer satisfactionReduced delays and cancellations

🧠 Technologies Used

Python (Google Colab environment)
scikit-learn — K-Means clustering
mlxtend — Apriori frequent itemset mining
pandas / numpy — Data processing
matplotlib / seaborn — Visualization


📄 License
This project was developed as part of a Data Mining course at ENSIA (École Nationale Supérieure d'Informatique), Algeria.
