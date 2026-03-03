📊 Rework Rate Analysis & SHF Validation
📌 Project Overview

This project performs structured data preprocessing and statistical validation on SHF (Soft Human Factors) variables to analyze their relationship with Rework Rate.

The objective is to:

Clean and validate structured project data

Detect and treat skewness & outliers

Normalize variables for consistency

Perform correlation analysis

Statistically validate significant relationships

This phase focuses on data preprocessing and feature validation before modeling.

🗂 Dataset

The dataset contains structured project-level metrics including:

Comment Frequency

Estimation Consistency

Other SHF-related indicators

Rework Rate (Target Variable)

Initial dataset format: Excel (.xlsx)

⚙️ Workflow & Methodology
1️⃣ Data Loading & Cleaning

Loaded dataset using pandas

Removed non-numeric metadata columns:

Project_ID

Project_Key

Project_Name

Checked:

Data types

Missing values

Dataset shape

2️⃣ Outlier Detection

Used boxplots to visually inspect extreme values

Applied IQR-based outlier detection

Evaluated skewness patterns

3️⃣ Log Transformation

Certain variables showed right-skewness.

Applied log1p() transformation to:

Comment_Frequency

Estimation_Consistency

Purpose:

Reduce skewness

Improve statistical stability

Enhance correlation reliability

4️⃣ Normalization

Applied MinMax Scaling:

X_scaled = (X - min) / (max - min)

Scaled all numeric features to range [0, 1]

Ensured uniform feature contribution

Exported clean dataset as:

normalized_shf.csv
5️⃣ Correlation Analysis

Performed:

Pearson Correlation

Spearman Correlation

Generated:

Heatmaps

Sorted correlation strength vs Rework_Rate

Objective:

Identify strongest SHF drivers of rework

6️⃣ Statistical Significance Testing

Used:

pearsonr

spearmanr

Computed:

Correlation coefficient (r / ρ)

p-values

Because of small sample size (n = 39), we evaluated:

α = 0.05

α = 0.10

Power analysis was performed using statsmodels to justify relaxed significance threshold.

🧪 Statistical Rigor

Additional validation included:

IQR-based outlier filtering

Significance threshold comparison (p < 0.05 vs p < 0.10)

Power estimation for correlation testing

This ensures:

Methodological reliability

Transparent statistical reasoning

Controlled Type I / Type II error considerations

🛠 Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

SciPy

Scikit-learn

Statsmodels

📈 Key Focus Areas

Data integrity validation

Feature transformation

Correlation robustness

Statistical justification of findings

Pre-model analytical reliability

📌 Output

Cleaned & normalized dataset (normalized_shf.csv)

Correlation heatmaps

Statistical significance results

Power analysis validation

🎯 Purpose of This Phase

This preprocessing and validation phase ensures:

Features are statistically sound

No misleading correlations

Dataset is modeling-ready

Results are reproducible and defensible

This project demonstrates structured analytical thinking, statistical rigor, and reliable data validation practices.
