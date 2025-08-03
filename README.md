# 📊 Social Media Engagement Analysis

This project investigates patterns of user engagement on social media platforms using both **supervised** and **unsupervised** machine learning techniques. It aims to help businesses understand, predict, and optimize engagement levels, enabling more effective content strategies and targeted marketing.

---

## 🎯 Project Objectives

* Segment social media users based on engagement behavior (clustering).
* Predict the likelihood of post engagement using ML classification.
* Generate business insights to inform data-driven marketing strategies.

---

## 🗂 Datasets

| Dataset                | Description                                                                                                  | Source                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| **Facebook Metrics**   | Contains post-level metrics such as likes, shares, comments, impressions, etc. Used for supervised learning. | [UCI Facebook Metrics](https://archive.ics.uci.edu/dataset/368/facebook+metrics)           |
| **Twitter Engagement** | Includes tweet-level data such as retweets, likes, and timestamps. Used for clustering users.                | [Kaggle Dataset](https://www.kaggle.com/datasets/thedevastator/tweets-and-user-engagement) |

---

## 🛠 Tools & Technologies

* **Python**
* Scikit-learn, Pandas, NumPy, Seaborn, Matplotlib, SHAP
* Jupyter Notebook
* PCA, K-Means Clustering, SVM, Random Forest
* Git & GitHub

---

## 🔄 Data Preprocessing

### For Facebook (Supervised Learning)

* Imputation: Median for missing `like`, `share`, `comment`; `Paid` → 0.
* Feature Engineering: `Engagement Rate` = (like + share + comment) / total page likes.
* One-Hot Encoding on post type.
* Z-score standardization on numerical features.

### For Twitter (Unsupervised Learning)

* Dropped non-informative fields (`Tweet_ID`, `Username`, `Text`).
* Engineered features:

  * `Hour`, `DayOfWeek`, `Engagement_Score`, `Like_to_Retweet_Ratio`
* Z-score normalization for clustering robustness.

---

## 🧠 Machine Learning Models

### 📌 Unsupervised Learning (Clustering)

* **Algorithm**: K-Means
* **Optimal K**: 7 (validated by Elbow Method and Silhouette Score ≈ 0.57)
* **PCA** used for dimensionality reduction and visualization.
* **Cluster Types**:

  * Power Users
  * Appreciators
  * Early/Late Week Amplifiers
  * Weekend Socializers
  * Early Morning Minimalists
  * Low-Activity Users

### 📌 Supervised Learning (Classification)

* Models Used:

  * Logistic Regression
  * Decision Tree
  * Random Forest (tuned)
  * Support Vector Machine (SVM & Tuned SVM)
  * LDA + Random Forest
* **Best Model**: Tuned SVM

  * F1-Score: **0.95**, ROC-AUC: **0.998**

---

## 📊 Evaluation Metrics

| Model               | Accuracy | Precision | Recall   | F1-Score | ROC-AUC   |
| ------------------- | -------- | --------- | -------- | -------- | --------- |
| Logistic Regression | 0.94     | 0.95      | 0.94     | 0.94     | 0.996     |
| Decision Tree       | 0.94     | 0.95      | 0.94     | 0.94     | 0.939     |
| Random Forest       | 0.97     | 0.97      | 0.97     | 0.97     | 0.995     |
| **Tuned SVM** ✅     | **0.95** | **0.95**  | **0.95** | **0.95** | **0.998** |
| LDA + RF            | 0.72     | 0.72      | 0.72     | 0.72     | 0.785     |

---

## 📌 Feature Importance & Interpretability

* **Feature Importance**: via Random Forest impurity and SHAP values.
* Top Predictors:

  * `like`, `Engagement_Rate`, `share`, `comment`, `Impressions`
* SHAP summary plots used for localized explanations and transparency.

---

## 💡 Business Insights

* High engagement is **driven by user actions** (likes, shares), not metadata.
* **Engagement Rate** is a key normalized metric for evaluating post success.
* **Organic interactions** outweigh the impact of paid content or post type.
* Use clustering for **user targeting** (e.g., reward Power Users, re-engage Low-Activity Users).

---

## 📈 Visualizations

* PCA cluster plots
* SHAP value summary plots
* Feature importance bar charts
* F1-score comparison charts

---

## 📁 Project Structure

```
📦 social-media-engagement-analysis
 ┣ 📂 data
 ┣ 📂 notebooks
 ┣ 📂 visualizations
 ┣ 📄 README.md
 ┣ 📄 requirements.txt
 ┗ 📄 main.ipynb
```

---

## 📌 How to Run

1. Clone the repository
   `git clone https://github.com/zx784/Social-Media-Engagement-Analysis.git`

2. Install requirements
   `pip install -r requirements.txt`

3. Run the notebooks
   Navigate to `/notebooks` and start exploring.

---

## 📚 References

* UCI Facebook Metrics Dataset
* Twitter User Engagement Dataset (Kaggle)
* SHAP Library by Lundberg

