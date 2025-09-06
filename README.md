# 📊💭 WorkWell: Data-Driven Mental Health Insights for Tech Professionals

## 🎯 Project Overview
Mental health challenges such as stress, anxiety, and burnout are increasingly common among tech professionals due to long working hours, high pressure, and remote/hybrid work culture. Despite this, many employees hesitate to seek support due to stigma, lack of awareness, or fear of discrimination.

**WorkWell** leverages survey data (2018–2023) to **analyze workplace mental health trends** and build **predictive models** to help organizations identify risk factors and understand employee comfort levels in discussing mental health at work.

---

## 📊 Dataset

**Source:** [OSMI Mental Health in Tech Survey](https://osmhhelp.org/research.html)  

**Overview:**  
The dataset consists of survey responses from tech professionals between **2018 and 2023**, capturing workplace mental health trends, perceptions, and policies. It focuses on factors affecting **stress, anxiety, burnout, and willingness to discuss mental health at work**.

**Key Features Include:**  
- **Demographics:** Age, gender, race, country, company size, role type.  
- **Workplace Factors:** Employer mental health benefits, formal discussions, awareness campaigns, leave policies, anonymity.  
- **Perceptions & Comfort:** Employee comfort discussing mental health with coworkers and supervisors, stigma perceptions, importance of mental vs. physical health.  
- **Experience:** Prior disclosures, family history of mental illness, prior employer support.

**Notes:**  
- Some responses contain `Unknown` or missing values, which were handled during preprocessing.  
- The dataset is primarily used for **EDA and predictive modeling** to identify risk factors and forecast comfort in disclosing mental health issues.

---

## 🛠️ Objectives
1. **Analyze survey trends** in workplace mental health over 5 years.
2. **Identify risk factors** such as lack of benefits, low openness, or absence of formal discussions.
3. **Predict employee comfort** in discussing mental health with coworkers and supervisors.
4. **Provide actionable insights** embedded within visualizations.

---

## 📈 Project Workflow

### 1. Data Preprocessing
- Handle missing values (`NaN`, `Unknown`) and standardize categorical variables (`Yes/No`, `True/False`).
- Encode demographics (age, gender, race, employer size).
- Convert target variables for ML models.

### 2. Exploratory Data Analysis (EDA)
- **Demographics:** Age, gender, race, employer size distributions.
- **Employer Policies & Resources:** Mental health benefits, formal discussions, awareness trends.
- **Comfort & Stigma:** Comfort levels with coworkers and supervisors.
- **Historical Trends:** Changes from 2018–2023.
- **Statistical Relationships:** Gender, age, employer size vs. willingness to disclose mental health issues.
- **Correlation Analysis:** Relationship between demographics, employer policies, and willingness to disclose.

> ✅ **Note:** Observations and actionable insights are **directly included below each visualization**.

---

## 🤖 Machine Learning Approach

### Target Variables
- **Comfort with Coworkers:** Would an employee feel comfortable discussing mental health issues with coworkers?  
- **Comfort with Supervisors:** Would an employee feel comfortable discussing mental health issues with supervisors?

---

### Model Performance – Coworkers Comfort
| Model                   | Accuracy | Precision (Macro) | Recall (Macro) | F1-Score (Macro) | Strengths                                                                          | Weaknesses                                                                 |
| ----------------------- | -------- | ----------------- | -------------- | ---------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| **Logistic Regression** | 0.64     | 0.69              | 0.68           | 0.68             | Simple, interpretable; perfect classification of *Unknown*.                        | Struggles with *Maybe* vs *Yes* overlap; moderate “No” detection.          |
| **Random Forest**       | 0.64     | 0.71              | 0.67           | 0.68             | High recall for *Maybe*; perfect *Unknown* detection.                              | Weak recall for *Yes*; many *Yes → Maybe* misclassifications.              |
| **XGBoost**             | 0.63     | 0.67              | 0.67           | 0.67             | Balanced performance across classes; strong *Unknown* detection.                   | Lower accuracy than Random Forest & CatBoost; struggles with *Yes* recall. |
| **CatBoost**            | **0.68** | **0.73**          | **0.71**       | **0.71**         | Best overall accuracy; strong performance for *Maybe* and *No*; perfect *Unknown*. | Recall for *Yes* is weaker (many *Yes → Maybe*).                           |

---

### Model Performance – Supervisor Comfort
| Model                   | Accuracy | Strengths                                                            | Weaknesses                                                                           | Key Insights                                                           |
| ----------------------- | -------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| **Logistic Regression** | ~58%     | Simple, interpretable baseline model.                                  | Struggles with complex, non-linear relationships.                                     | Useful as a benchmark but not sufficient for nuanced predictions.      |
| **Random Forest**       | ~61%     | Handles non-linearity well, robust against overfitting.               | Moderate accuracy, tends to confuse “Maybe” and “Yes”.                                | Performed better than Logistic Regression but limited generalization.  |
| **XGBoost**             | ~60%     | Strong gradient boosting algorithm, effective for structured data.    | Accuracy not significantly better than Random Forest; “Maybe” class misclassified often. | Stable performance, but tuning is critical for improvements.           |
| **CatBoost**            | **65%**  | Best accuracy among tested models; handles categorical data efficiently. | “Maybe” class still weak; longer training time.                                       | Most reliable so far, especially strong in classifying “Unknown” and “No”. |

---

## 🔬 Key Insights
- Observations and insights are **embedded below each EDA visualization**.
- Employees in smaller companies are less likely to have mental health benefits compared to larger companies.
- Gender and race influence willingness to discuss mental health.
- Employer policies, formal campaigns, and awareness improve comfort levels.
- Comfort with coworkers is generally higher than comfort with supervisors.

---

## 💼 Business Value
- Helps organizations identify high-risk groups who may not disclose mental health issues.
- Provides actionable insights for HR policy improvement: awareness campaigns, training, benefits.
- Supports data-driven decision-making for employee wellness initiatives.

---

## 🗂️ Deliverables
1. **GitHub Repository:** Code, cleaned dataset, ML models.
2. **EDA Analysis & Visualizations:** Histograms, bar plots, correlation analysis with insights directly below visuals.

---

## 🛠️ Tech Stack
- Python (Pandas, NumPy, Scikit-learn, XGBoost, CatBoost, Matplotlib, Seaborn, Plotly)
- GitHub for version control and collaboration

---

## 📌 Conclusion
**WorkWell** demonstrates an **end-to-end mental health analytics workflow**, including data preprocessing, EDA, and predictive modeling. Insights are **directly embedded within visualizations**, making the analysis intuitive and actionable for organizations seeking to improve workplace mental health.

---

## 👤 Author  
**Khushi Gupta**  
📧 Email: [khushig2882@gmail.com](mailto:khushig2882@gmail.com)  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/khushi-gupta-5892772b6/)  

---

