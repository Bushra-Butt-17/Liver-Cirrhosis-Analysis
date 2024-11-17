

```markdown
# Liver Cirrhosis Analysis

## Project Overview

This project provides an in-depth analysis of **Liver Cirrhosis** using clinical data. The goal is to explore how various biomarkers (such as **Bilirubin**, **Copper**, **Alkaline Phosphatase**) and patient demographics (such as **Age**, **Sex**) influence the progression of the disease. The analysis investigates different stages of cirrhosis and includes an exploration of gender differences, disease severity, and possible predictors of mortality or liver transplant needs.

### Key Features:
- Data exploration and visualization to identify key clinical indicators of liver cirrhosis.
- Comparison of biomarkers across different stages of cirrhosis.
- Cross-tabulation and visualization of **gender** differences in disease progression.
- Statistical analysis of **age-related trends** in cirrhosis stage progression.
- Insights into survival rates and the likelihood of liver transplant in advanced stages.

---

## Table of Contents

1. [Installation Instructions](#installation-instructions)
2. [Usage](#usage)
3. [Data Overview](#data-overview)
4. [Analysis](#analysis)
   - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
   - [Statistical Analysis](#statistical-analysis)
5. [Visualizations](#visualizations)
6. [Contributors](#contributors)
7. [License](#license)

---

## Installation Instructions

Follow these steps to set up this project locally:

### Requirements:
- Python 3.x
- Required Libraries: `pandas`, `matplotlib`, `seaborn`, `scipy`, `numpy`

### Step 1: Clone the Repository
Clone the repository to your local machine:

```bash
git clone https://github.com/Bushra-Butt-17/Liver-Cirrhosis-Analysis.git
```

### Step 2: Install Required Libraries
Navigate to the project folder and install the necessary libraries:

```bash
cd Liver-Cirrhosis-Analysis
pip install -r requirements.txt
```

### Step 3: Run the Jupyter Notebook or Python Script
Once the libraries are installed, you can open the Jupyter Notebook or run the Python scripts to perform the analysis and visualizations.

---

## Usage

This project is designed for researchers, healthcare professionals, and data scientists who are interested in understanding the progression of liver cirrhosis. It includes the following aspects:

- **Clinical Research**: Understanding how biomarkers like **Bilirubin**, **Copper**, and **Alkaline Phosphatase** correlate with liver disease progression.
- **Predictive Modeling**: Using clinical data to predict the stage of liver cirrhosis and outcomes such as liver transplant or mortality.
- **Educational Use**: This project serves as a practical example of how data science can be applied to medical research.

To use this project:

1. Open the Jupyter Notebook or execute the Python scripts.
2. The dataset will be loaded automatically (ensure the file path is correct).
3. Follow the steps in the notebook to clean the data, perform the analysis, and visualize results.

---

## Data Overview

The dataset used for this project contains clinical data for liver cirrhosis patients, including the following columns:

- **Age**: Patient's age.
- **Sex**: Patient's gender (M/F).
- **Stage**: Stage of liver cirrhosis (1 to 4, with 4 being the most advanced).
- **Bilirubin**: Serum Bilirubin level, a marker of liver function.
- **Copper**: Copper levels in the bloodstream, relevant to liver cirrhosis.
- **Alk_Phos**: Alkaline Phosphatase, an enzyme indicating liver dysfunction.
- **Albumin**: Protein levels, low values suggest liver damage.
- **Cholesterol**: Serum cholesterol levels, influenced by liver health.
- **SGOT**: Serum Glutamic Oxaloacetic Transaminase, another liver enzyme.
- **Platelets**: Platelet count, often lower in cirrhosis.
- **Prothrombin**: Blood clotting, impacted by liver function.

Example Data:

| Stage | Age | Sex | Bilirubin | Copper | Alk_Phos | SGOT | Cholesterol | Albumin | Platelets | Prothrombin |
|-------|-----|-----|-----------|--------|----------|------|-------------|---------|-----------|-------------|
| 1     | 45  | M   | 2.0       | 100    | 150      | 80   | 200         | 3.5     | 300,000   | 11.2        |
| 2     | 60  | F   | 3.5       | 150    | 220      | 100  | 190         | 3.2     | 280,000   | 10.8        |
| 3     | 70  | M   | 5.0       | 200    | 300      | 120  | 180         | 2.9     | 250,000   | 10.5        |

---

## Analysis

### Exploratory Data Analysis (EDA)

EDA includes various techniques to understand the dataset:

- **Descriptive statistics**: Summary statistics like mean, median, and standard deviation.
- **Outlier detection**: Identifying data points that significantly differ from others.
- **Correlation analysis**: Investigating relationships between biomarkers and stages.

#### Example Code:
```python
# Calculate mean values by gender for selected columns
df.groupby('Sex')[['Age', 'Bilirubin', 'Copper', 'Alk_Phos']].mean()
```

### Statistical Analysis

In this step, statistical tests are used to compare biomarkers across different stages of liver cirrhosis:

- **T-tests**: Compare biomarkers between stages.
- **ANOVA**: Determine significant differences between multiple groups.
- **Survival Analysis**: Predict the likelihood of mortality or liver transplant in advanced stages.

#### Example of T-test:
```python
from scipy import stats
stage_1 = df[df['Stage'] == 1]['Bilirubin']
stage_3 = df[df['Stage'] == 3]['Bilirubin']
t_stat, p_value = stats.ttest_ind(stage_1, stage_3)
print(f"T-statistic: {t_stat}, P-value: {p_value}")
```

---

## Visualizations

This project includes several visualizations to help understand the data:

- **Stacked Bar Chart**: Distribution of liver cirrhosis stages by gender.
- **Heatmap**: Correlation matrix of biomarkers.
- **Boxplot**: Distribution of biomarkers for each disease stage.

#### Example Code for Stacked Bar Chart:
```python
df.groupby(['Stage', 'Sex']).size().unstack().plot(kind='bar', stacked=True)
plt.title('Distribution of Stages by Gender')
plt.xlabel('Stage')
plt.ylabel('Count')
plt.show()
```

#### Example Code for Heatmap:
```python
import seaborn as sns
correlation_matrix = df[['Bilirubin', 'Copper', 'Alk_Phos', 'SGOT', 'Platelets']].corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap of Biomarkers')
plt.show()
```

---


Feel free to contribute by opening issues, forking the repository, and submitting pull requests!

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
```


