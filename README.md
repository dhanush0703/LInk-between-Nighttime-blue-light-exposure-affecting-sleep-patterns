# LInk-between-Nighttime-blue-light-exposure-affecting-sleep-patterns
A data science study examining how nighttime blue light exposure from digital devices (smartphones, laptops, TVs) affects sleep quality among young adults, combining survey research, statistical analysis, Power BI dashboards, and machine learning.

## 👥 Team

- Dhanush Hegde
- Ritesh Sanjay Kulkarni
- Mohammed Parveez C
- Rohith G

## 📋 Problem Statement

Excessive nighttime exposure to blue light from smartphones, laptops, desktops, and TVs is increasingly suspected to interfere with sleep quality. This study quantitatively examines the correlation between nighttime screen usage — specifically blue light exposure — and sleep quality indicators such as total sleep duration, sleep latency, and frequency of nighttime awakenings.

## 🧠 Background & Motivation

Evening exposure to blue-rich light suppresses melatonin production, delaying sleep onset and fragmenting the circadian rhythm. Late-night screen use is pervasive among young adults, who often multitask across devices and report feeling unrefreshed despite adequate time in bed. This project moves beyond anecdote to quantify the relationship using survey data, aiming to inform healthier digital habits and device design (e.g., adaptive color-temperature features).

## 🎯 Target Audience

Applicable broadly across age groups, but the study focuses on **19–23 year olds** (college students / early-career professionals) — a demographic with especially high evening screen engagement.

## 📚 Literature Review Summary

| Source | Key Finding |
|---|---|
| Yüksel & Peker (2023) | Blue light delays melatonin release; impairs student attention/memory |
| Christensen et al. (2024) | Screen use within 2 hrs of bedtime reduces total sleep, increases fragmentation |
| Wang et al. (2024) | Blue light reduces deep (slow-wave) sleep and morning alertness |
| Cain & Gradisar (2010) | Adolescent screen use delays circadian sleep phase |
| Chang et al. (2022) | Screen use after 10 PM most strongly linked to fatigue/irritability |

**Consistent theme:** Blue light exposure after 10 PM correlates with delayed sleep, poorer sleep quality, and reduced daytime performance — with young adults (19–23) at particular risk.

## 🔬 Hypotheses

- **H₁ (Research):** Nighttime blue light exposure is significantly associated with poorer sleep quality — longer latency, less total sleep, more awakenings, lower perceived quality.
- **H₀ (Null):** No significant association exists between nighttime blue light exposure and these sleep metrics.

**Independent Variable:** Blue light exposure time (screen use after 10 PM)
**Dependent Variables:** Sleep latency, total sleep time, number of awakenings, perceived sleep quality (1–10 Likert)

**Expected relationships:** Positive correlation with sleep latency/awakenings; negative correlation with total sleep time/perceived quality.

## 🧪 Methodology

### Sampling
- **Population:** Ages 19–23 (college students / early-career professionals)
- **Technique:** Convenience sampling (primary), with optional stratified sampling across gender, stream of study, and screen-time habits for better representativeness
- **Sample size target:** 100–150 participants (100+ responses collected)
- **Inclusion:** Age 19–23, ≥2 hrs/day device use, willing to self-report honestly
- **Exclusion:** Diagnosed sleep disorders/medication, night-shift workers, incomplete responses

### Data Collection
- Structured **Google Forms** survey (15 questions covering screen habits, blue-light filter use, multitasking, sleep latency, awakenings, restfulness, sleep schedule consistency, and caffeine intake)
- Exported to **CSV**, cleaned and analyzed with **Python (Pandas)**, **Excel**, and **Power BI**

### Data Cleaning & Privacy
- Removed/anonymized personally identifying fields (name, email)
- Parsed and standardized date-of-birth → derived age → binned into age groups
- Normalized inconsistent categorical labels (e.g., gender, field of study abbreviations)
- Re-binned free-form time responses into unified slots (Before 10 PM / 10 PM–12 AM / After 12 AM)
- Handled outliers in screen-time data using the IQR method
- Mapped ordinal responses (Never/Rarely/Sometimes/Always) to numeric scores (0–3) for correlation analysis

## 📊 Key Statistical Findings

- Average screen time: **2.42 hrs/day** (SD 1.69 hrs); max reported 10 hrs
- Average sleep latency: **20.62 minutes**
- Average weekday sleep: **7.29 hours**
- Average respondent age: **24.35 years**
- Most students stop screen use between **11 PM–12 AM**
- Gender split: 43 male, 42 female (near-even)
- Largest field-of-study group: Computer Science/IT (44 respondents)
- Most respondents "Always" or "Sometimes" use blue-light filters
- Most common multitasking frequency: "Occasionally"

## 📈 Power BI Dashboard

An interactive dashboard ("Impact of Night Time Blue-Light Exposure on Sleep Patterns") with slicers for gender and primary night activity, featuring:

| Visual | Purpose |
|---|---|
| KPI Cards | Total count, average age, average weekday sleep, average screen hrs after 10 PM, average sleep latency |
| Stacked Bar — Sleep vs. Restfulness by Field | Compares restfulness across academic fields |
| Bar Chart — Blue-Light Filter Usage | Counts of Always/Sometimes/Rarely/Never |
| Bar Chart — Weekday Sleep by Restfulness | Sleep hours grouped by restfulness rating |
| Donut Chart — Caffeine Consumption After 6 PM | Daily / 2–3×/week / Occasionally / Never |
| Bar Chart — Restfulness After Waking Up | Often/Sometimes/Rarely/Always |
| Pie Chart — Sleep Schedule Consistency | Most days / Rarely / Always / Never |

The dashboard supports drill-down via slicers (date, demographic, category) for tailored analysis and stakeholder reporting.

## 🤖 Machine Learning & Correlation Analysis

Three scatter plots with regression lines were used to explore relationships between digital habits and a derived **Health Score**:

1. **Screen Time vs. Night Mode Usage** — tests whether frequent night-mode users spend less time on screens (screen discipline indicator)
2. **Screen Time vs. Multitasking Frequency** — tests whether heavier multitaskers report higher screen time
3. **Night Mode Usage vs. Health Score** — tests whether night-mode use is associated with better health/sleep outcomes

### Predictive Models

| Model | Metric | Result |
|---|---|---|
| Random Forest (Classification) | Accuracy | ~91% |
| Support Vector Regressor (SVR) | MSE / R² | 0.156 / 0.376 |
| Random Forest (Regression) | MSE / R² | 0.091 / 0.636 |

Random Forest outperformed other models for classifying poor vs. good sleep, while SVR added a more granular, continuous view of sleep-quality scores.

## ✅ Conclusion

The project found a clear, measurable link between nighttime digital behavior — screen time, blue-light filter use, and multitasking — and sleep quality among young adults. Behavioral variables such as late-night screen exposure and inconsistent sleep hygiene were strongly associated with disrupted sleep. Random Forest was the most robust classifier (~91% accuracy), while SVR added nuance in predicting the degree of sleep disruption, demonstrating how machine learning can effectively model behavioral health data.

## 🧰 Tools Used

- **Google Forms** – survey design and distribution
- **Python (Pandas, scikit-learn)** – data cleaning, SVR/Random Forest modeling
- **Microsoft Excel** – supplementary cleaning and summary stats
- **Power BI** – interactive dashboard and visual analytics

---
*This README summarizes the final submission report for the "Link Between Nighttime Blue Light Exposure and Sleep Patterns" project 
