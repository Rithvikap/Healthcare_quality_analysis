# US Hospital Quality Intelligence Analysis
**Analyst:** Rithvika Paladugu | MS Data Science, Stevens Institute of Technology
**Data Source:** CMS Hospital Compare (data.cms.gov)  
**Tools:** Python (Pandas, Matplotlib, Seaborn) | Tableau Public  
**Live Dashboard:** https://public.tableau.com/app/profile/rithvika.paladugu/viz/USHospitalQualityIntelligenceCMSAnalysis/Dashboard1

---

## Business Context
*Simulated scenario:* A regional hospital network's CMO needs to 
benchmark hospital quality before a board review. As the analyst, 
I structured the problem around three strategic questions before 
touching any data — a discipline that separates reactive reporting 
from proactive analysis.

---

## Dataset
- **Hospital General Information:** 5,432 US hospitals, 38 features
- **Complications & Deaths Quality Measures:** 95,840 rows, long format
- Both sourced from data.cms.gov — real federal government data

---

## Key Findings
1. **Geographic gap:** Top performing states (MD, MA, NJ) average 5.8 points 
   above the national average of 8.43, while bottom states average 4.8 points 
   below — a 10.6 point performance gap suggesting significant geographic 
   inequality in US hospital quality
2. **Rating distribution:** 42% of rated hospitals perform above average, 
   but 2,250 hospitals (41% of all facilities) have no CMS rating — 
   a significant blind spot in quality assessment
3. **Ownership impact:** Non-profit hospitals lead with 9.2 average quality 
   score vs 6.9 for government-owned — structural advantages including 
   academic affiliations and philanthropic funding drive this gap
4. **VA surprise:** VA hospitals score highest among all hospital types 
   at 15.68 — 7.17 points above national average — directly contradicting 
   public perception of VA healthcare quality
5. **Rating drivers:** No single factor dominates star ratings. Readmission 
   performance is the strongest predictor (r=0.38), while safety performance 
   shows almost no correlation (r=0.07)

---
## Project Structure
```
healthcare-quality-analysis/
├── Healthcare_Quality_Analysis.ipynb  # Full Python analysis
├── healthcare_analysis_clean.csv      # Cleaned merged dataset
├── executive_summary.pdf              # CMO-ready findings report
├── viz1_state_quality.png
├── viz2_rating_distribution.png
├── viz3_ownership_quality.png
├── viz4_type_quality.png
└── viz5_correlation_heatmap.png
```
---
## Technical Approach
- **ETL:** Merged two CMS datasets on Facility ID, replaced 'Not Available' 
  strings with NaN, converted 19 object columns to numeric, engineered 
  composite Quality Performance Score from MORT/Safety/READM components
- **EDA:** 5 targeted visualizations answering specific business questions
- **Tableau:** Interactive dashboard with state-level filter controlling 
  all views simultaneously
