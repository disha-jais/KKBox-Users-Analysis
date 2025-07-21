# 🎧 Cracking the Code: Why KKBox Users Churn

Understanding why users leave a platform is essential for improving retention in any subscription-based service — and KKBox is no exception. This project uses real-world churn data to uncover **patterns**, **drivers**, and **insights** behind user attrition.

---

## 🎯 Project Goals

- Identify the **key factors** driving user churn  
- Analyze **demographics**, **registration methods**, and **regional behavior**  
- Provide **actionable business insights** to improve retention

---

## 📁 Data Overview

This project uses two datasets:

- `train_v2.csv`: User churn labels with behavioral features  
- `members_v3.csv`: Demographic details (age, gender, city, registration method)

### 🔑 Key Variables

| Column           | Description                                   |
|------------------|-----------------------------------------------|
| `msno`           | Unique user ID                                |
| `is_churn`       | Target label (1 = churned, 0 = retained)       |
| `gender`         | Male/Female                                   |
| `bd`             | Birth date (used to calculate age)            |
| `city`           | City code (later mapped to real names)        |
| `registered_via` | Registration channel/platform ID              |

---

## 🧠 Key Insights

### 👥 **Age Matters**

- **18–29** age group has the **highest churn** (~14.8%)  
- Users under 18 and over 50 have **lower churn** (~6.8–9.9%)

### 🌍 **Regional Retention Gaps**

- Cities like **Taoyuan**, **New Taipei**, and **Tainan** show **above-average churn**
- **Taipei** stands out with the **lowest churn (~6.4%)**

### 🖥️ **Registration Method**

- Method **4** has the **highest churn** (23.1%)  
- Methods **9** and **7** show **strong retention** (4.5–12.7%)

### 🚻 **Gender Parity**

- Churn rates for male and female users are **nearly identical**
- Gender is **not a significant predictor** in this case

---

## 📊 Visual Explorations

This project includes rich visualizations built using:

- **Pandas** for data wrangling  
- **Seaborn & Matplotlib** for charts and EDA  
- Custom mapping for city codes → real city names (e.g., Taipei, Taoyuan)

Example charts:
- Churn distribution  
- Churn by gender  
- City-wise churn (named regions)  
- Age group comparison  
- Churn by registration method

---

## 🧪 Sample Code Snippet

```python
# Calculate churn rate by age group
bins = [0, 18, 25, 35, 45, 60, 100]
labels = ['<18', '18–25', '26–35', '36–45', '46–60', '60+']
train_merged['age_group'] = pd.cut(train_merged['bd'], bins=bins, labels=labels)

age_churn = train_merged.groupby('age_group')['is_churn'].mean() * 100
```

---

## 🔍 Business Questions Answered

1. Are men or women more likely to churn? → **No significant difference**
2. Do some cities have unusually high churn? → **Yes (e.g., Taoyuan, Tainan)**
3. Does the way users register influence churn? → **Yes, dramatically**
4. Does user age affect churn? → **Yes, younger users are more likely to churn**

---

## 💡 Final Recommendations

| Recommendation                                      | Action Item                                        |
|-----------------------------------------------------|----------------------------------------------------|
| 🎯 Target 18–29 Users                               | Youth-focused campaigns & retention initiatives   |
| 🛠️ Improve Onboarding for Method 3 & 4             | Review user flows, address drop-off points        |
| 🗺️ Focus on High-Churn Cities                      | Tailored outreach in Taoyuan, New Taipei, Tainan  |
| 🧪 Create Samples for Testing                      | Sample datasets saved for reproducible testing    |

---

## 🔄 Reproducibility

To speed up development and sharing:

```python
# Save 300-row samples
train_sample = train_df.sample(n=300, random_state=1)
members_sample = members_df.sample(n=300, random_state=1)

train_sample.to_csv("data/train_v2_sample.csv", index=False)
members_sample.to_csv("data/members_v3_sample.csv", index=False)
```

---

## 📚 Skills Applied

- 🧹 Data Cleaning & Merging  
- 📊 Exploratory Data Analysis (EDA)  
- 🔍 Insight-Driven Storytelling  
- 🐍 Python: `pandas`, `matplotlib`, `seaborn`

---

## ✅ Project Outcome

From raw CSVs to actionable insights, this analysis tells a clear story around **why users churn**, with strong visuals and solid recommendations to improve **user retention** at KKBox.

---

## 📬 Contact

Made with ❤️ by [Disha]  
Got feedback or suggestions? Open an issue or connect via GitHub!


