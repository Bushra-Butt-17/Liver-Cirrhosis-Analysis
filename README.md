
---

# 🩺 Liver Cirrhosis Analysis

## 📝 Project Overview

This project provides an in-depth analysis of **Liver Cirrhosis** using clinical data. The objective is to explore the relationship between various **biomarkers** (e.g., **Bilirubin**, **Copper**, **Alkaline Phosphatase**) and **patient demographics** (e.g., **Age**, **Sex**) to understand the progression of the disease. 

### 🌟 Highlights:
- 🔍 **Data Exploration**: Visualizing clinical indicators of liver cirrhosis.  
- 📊 **Biomarker Comparisons**: Analysis of biomarkers across different disease stages.  
- 🧑‍🤝‍🧑 **Gender Differences**: Exploring male and female variations in disease progression.  
- 🎂 **Age Trends**: Statistical insights into age-related disease patterns.  
- 💡 **Survival Insights**: Predicting survival rates and the likelihood of liver transplant for advanced stages.

---

## 📚 Table of Contents

1. [📥 Installation Instructions](#installation-instructions)  
2. [🛠️ Usage](#usage)  
3. [📊 Data Overview](#data-overview)  
4. [🧮 Analysis](#analysis)  
   - [📋 Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
   - [📈 Statistical Analysis](#statistical-analysis)  
5. [🎨 Visualizations](#visualizations)  
6. [👩‍💻 Contributors](#contributors)  
7. [📜 License](#license)  

---

## 📥 Installation Instructions

### ✅ Requirements:
- Python 3.x  
- Required Libraries:
  - 📦 `pandas` for data manipulation  
  - 🎨 `matplotlib` and `seaborn` for visualizations  
  - 🧮 `scipy` and `numpy` for statistical computations  

### 🚀 Steps to Set Up:
1. **Clone the Repository**  
   ```bash
   git clone https://github.com/Bushra-Butt-17/Liver-Cirrhosis-Analysis.git
   ```

2. **Install Dependencies**  
   Navigate to the project directory and install all required libraries:  
   ```bash
   cd Liver-Cirrhosis-Analysis
   pip install -r requirements.txt
   ```

3. **Run the Project**  
   Open the Jupyter Notebook or Python scripts:  
   ```bash
   jupyter notebook
   ```

---

## 🛠️ Usage

This project serves **researchers**, **data scientists**, and **healthcare professionals** by enabling them to:  
- Examine correlations between biomarkers and liver disease progression.  
- Predict outcomes like liver transplants or mortality.  
- Use the provided codebase for clinical or educational purposes.

### 🔧 How to Use:
1. Load the dataset (ensure the correct file path).  
2. Follow the structured steps in the notebook for:
   - Data cleaning.  
   - EDA.  
   - Statistical analysis and visualizations.  
3. Interpret the outputs to draw meaningful insights.

---

## 📊 Data Overview

The dataset contains clinical information for liver cirrhosis patients. Key columns include:  

| 🏷️ Feature      | 📝 Description                                                                 |
|------------------|-------------------------------------------------------------------------------|
| **Age**         | Patient's age.                                                               |
| **Sex**         | Gender (M/F).                                                                |
| **Stage**       | Stage of liver cirrhosis (1 to 4).                                           |
| **Bilirubin**   | Serum Bilirubin levels (marker of liver function).                           |
| **Copper**      | Blood Copper levels (relevant for cirrhosis).                                |
| **Alk_Phos**    | Alkaline Phosphatase (enzyme indicating liver dysfunction).                  |
| **Albumin**     | Protein levels (lower levels suggest liver damage).                         |
| **SGOT**        | Serum Glutamic Oxaloacetic Transaminase (liver enzyme).                      |
| **Platelets**   | Platelet count (typically lower in cirrhosis).                               |
| **Prothrombin** | Blood clotting time, impacted by liver function.                             |

Sample Data:  

| Stage | Age | Sex | Bilirubin | Copper | Alk_Phos | SGOT | Albumin | Platelets | Prothrombin |
|-------|-----|-----|-----------|--------|----------|------|---------|-----------|-------------|
| 1     | 45  | M   | 2.0       | 100    | 150      | 80   | 3.5     | 300,000   | 11.2        |
| 2     | 60  | F   | 3.5       | 150    | 220      | 100  | 3.2     | 280,000   | 10.8        |

---

## 🧮 Analysis

### 📋 Exploratory Data Analysis (EDA)
EDA techniques include:  
- Descriptive statistics: Summary measures (mean, median, etc.).  
- Outlier detection.  
- Correlation analysis.  

#### Sample Code:
```python
# Calculate average biomarkers by gender
df.groupby('Sex')[['Age', 'Bilirubin', 'Copper']].mean()
```

### 📈 Statistical Analysis
Advanced techniques to uncover patterns:  
- **T-tests**: Comparing biomarker levels between two groups.  
- **ANOVA**: Testing significant differences across multiple stages.  
- **Survival Analysis**: Predicting outcomes like mortality or transplants.  

#### Example:
```python
from scipy import stats
stage_1 = df[df['Stage'] == 1]['Bilirubin']
stage_3 = df[df['Stage'] == 3]['Bilirubin']
t_stat, p_value = stats.ttest_ind(stage_1, stage_3)
print(f"T-statistic: {t_stat}, P-value: {p_value}")
```

---

## 🎨 Visualizations

Visualizations include:  
- 📊 **Stacked Bar Chart**: Gender distribution across cirrhosis stages.  
- 🧮 **Heatmap**: Correlations between biomarkers.  
- 📦 **Boxplots**: Variability of biomarkers by disease stage.  

#### Sample Visualization Code:
```python
import seaborn as sns
correlation_matrix = df[['Bilirubin', 'Copper', 'Alk_Phos']].corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Biomarker Correlation Heatmap')
plt.show()
```

---

## 👩‍💻 Contributors

Feel free to contribute by:  
1. Reporting issues.  
2. Opening pull requests.  
3. Enhancing the analysis or visualizations.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

### 🏷️ Tags: 
`Python` `Data Analysis` `Visualization` `Medical Research` `Statistical Analysis` `Seaborn` `Matplotlib` `Pandas`
