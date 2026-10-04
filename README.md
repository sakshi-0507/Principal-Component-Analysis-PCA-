# HealthLens: Revealing the Hidden Dimensions of Lifestyle Data

## Project Overview

**HealthLens** is a data science project that uses **Principal Component Analysis (PCA)** to uncover hidden patterns in lifestyle and health-related data.

The dataset contains different health and lifestyle factors such as sleep duration, sleep quality, physical activity, stress level, heart rate, daily steps, and age. Since many of these variables can be related to each other, PCA is used to reduce the dimensionality of the data while preserving the most important information.

The project helps transform complex health data into a smaller number of meaningful **Principal Components** that are easier to analyze and visualize.

---

## Objectives

* Analyze lifestyle and health-related data.
* Perform data cleaning and exploratory data analysis.
* Identify relationships between health and lifestyle variables.
* Standardize numerical features before applying PCA.
* Reduce the dimensionality of the dataset using PCA.
* Determine the optimal number of principal components.
* Analyze explained variance and PCA loadings.
* Visualize the reduced dataset using principal components.
* Identify hidden dimensions in lifestyle and health behavior.

---

## Dataset

**Dataset:** Sleep Health and Lifestyle Dataset

**Source:** Kaggle

The dataset contains information related to:

* Age
* Gender
* Occupation
* Sleep Duration
* Quality of Sleep
* Physical Activity Level
* Stress Level
* BMI Category
* Blood Pressure
* Heart Rate
* Daily Steps
* Sleep Disorder

For PCA, the main numerical features used in the analysis are:

```text
Age
Sleep Duration
Quality of Sleep
Physical Activity Level
Stress Level
Heart Rate
Daily Steps
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Feature Selection
   ↓
Feature Standardization
   ↓
Principal Component Analysis
   ↓
Explained Variance Analysis
   ↓
Scree Plot
   ↓
PCA Loadings
   ↓
Dimensionality Reduction
   ↓
2D Visualization
   ↓
Component Interpretation
   ↓
Conclusion
```

---

## Exploratory Data Analysis

The following analysis was performed:

### 1. Age Distribution

Analyzed the distribution of age across the dataset.

### 2. Sleep Duration Distribution

Examined how many hours people sleep and the overall distribution of sleep duration.

### 3. Physical Activity vs Stress

Analyzed the relationship between physical activity levels and stress levels.

### 4. Correlation Heatmap

A correlation heatmap was created to understand relationships between numerical lifestyle and health variables.

---

## PCA Methodology

### 1. Feature Selection

The relevant numerical variables were selected for PCA:

```python
features = [
    "Age",
    "Sleep Duration",
    "Quality of Sleep",
    "Physical Activity Level",
    "Stress Level",
    "Heart Rate",
    "Daily Steps"
]

X = df[features]
```

### 2. Standardization

Since the variables have different scales, StandardScaler was used:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

### 3. PCA

PCA was applied to the standardized data:

```python
from sklearn.decomposition import PCA

pca = PCA()
X_pca = pca.fit_transform(X_scaled)
```

### 4. Explained Variance

The explained variance ratio was calculated to understand how much information each principal component retains.

```python
explained_variance = pca.explained_variance_ratio_
```

### 5. Cumulative Explained Variance

Cumulative explained variance was used to determine the number of components required to preserve most of the information.

```python
cumulative_variance = np.cumsum(explained_variance)
```

---

## PCA Loadings

PCA loadings were analyzed to understand how strongly each original feature contributes to each principal component.

```python
loadings = pd.DataFrame(
    pca_final.components_.T,
    columns=pca_columns,
    index=features
)
```

The loading values help interpret the underlying meaning of each principal component.

For example, if a component has strong contributions from sleep duration, quality of sleep, and physical activity, it can be interpreted as a **healthy lifestyle dimension**.

---

## Visualizations

The project includes the following visualizations:

* Age Distribution
* Sleep Duration Distribution
* Physical Activity vs Stress
* Correlation Heatmap
* Scree Plot
* Cumulative Explained Variance Plot
* PCA Loading Heatmap
* PCA 2D Scatter Plot
* PCA Visualization by Sleep Disorder
* PCA Visualization by BMI Category

---

## Key Insights

* Lifestyle and health variables contain relationships that can be summarized using PCA.
* PCA reduces the number of dimensions while retaining most of the important information.
* Sleep, physical activity, stress, heart rate, and daily activity contribute to different underlying patterns.
* The explained variance helps determine how many principal components are sufficient for analysis.
* PCA loadings provide an interpretable way to understand the contribution of each lifestyle variable.
* The 2D PCA visualization makes complex multidimensional health data easier to understand.

---

## Business / Practical Applications

The approach used in HealthLens can be useful for:

* Health and wellness analytics
* Lifestyle pattern analysis
* Personalized wellness applications
* Sleep and fitness analytics
* Healthcare data visualization
* Behavioral research
* Dimensionality reduction before machine learning

---

## Conclusion

The **HealthLens** project successfully demonstrates the use of **Principal Component Analysis (PCA)** for analyzing complex lifestyle and health data.

By standardizing the numerical variables and applying PCA, multiple correlated health and lifestyle factors were transformed into a smaller set of principal components while preserving most of the important information.

The PCA loadings helped identify the variables that contribute most strongly to each hidden dimension, while the visualizations made the reduced data easier to interpret.

Overall, **HealthLens shows how PCA can simplify high-dimensional health data, reveal hidden lifestyle patterns, reduce complexity, and support more effective data-driven analysis.**

---

## Future Improvements

Future versions of HealthLens could include:

* Applying clustering algorithms to the PCA components.
* Building a lifestyle-risk prediction model.
* Creating an interactive Power BI or Tableau dashboard.
* Adding more health and lifestyle variables.
* Using machine learning for personalized health recommendations.
* Developing an interactive web application for lifestyle analysis.

---

## Project Structure

```text
HealthLens/
│
├── HealthLens_PCA.ipynb
├── Sleep_health_and_lifestyle_dataset.csv
├── HealthLens_PCA_Dataset.csv
├── README.md
└── images/
    ├── correlation_heatmap.png
    ├── scree_plot.png
    ├── explained_variance.png
    ├── pca_loadings.png
    └── pca_visualization.png
```

---

## Skills Demonstrated

**Python | Pandas | NumPy | Data Cleaning | EDA | Data Visualization | Feature Scaling | PCA | Dimensionality Reduction | Statistical Analysis | Data Interpretation**

---

## Author

**Sakshi Bagul**

Data Science & Analytics | Machine Learning | Generative AI
