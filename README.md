# project_w7

# 🧠 Predicting Alzheimer’s Disease from Symptom Data

## 📌 Project Overview
This project aims to predict whether a patient has Alzheimer’s disease based on clinical and symptom data.  
Alzheimer’s is a serious neurodegenerative condition, and early detection can significantly improve care and intervention strategies. Traditional diagnosis often requires expensive imaging or invasive tests.  
Our goal was to build an accessible, data-driven Machine Learning model to assist in diagnosis or screening using **symptom and clinical features**.

---

## 🧑‍⚕️ Project Question
> *Given patient symptom and clinical features, can we accurately predict the presence of Alzheimer’s disease?*

---

## 🧾 Data Sources

- **Dataset**: *“Alzheimer’s Disease Dataset”* by Rabie El Kharoua - definitions of each columns below on Demographichs Information.
  Source: [Kaggle](https://www.kaggle.com/)  
- **Size**: 2,149 patient records  
- **Features**: Clinical, demographic, and symptom variables (categorical & numerical)  
- **Target**: Alzheimer’s diagnosis (binary: 0 = No, 1 = Yes)

---

## 🧹 Data Preparation

- Dropped identifying columns (patient name, doctor name) to avoid data leakage and protect privacy.  
- Checked for missing values, outliers, and inconsistencies.  
- Encoded categorical variables (e.g., binary symptom flags) and scaled numerical features when necessary.  
- Separated features and target, split into training and testing sets.

---

## 🧮 Feature Engineering & Selection

To improve model interpretability and performance, we selected the top five most correlated features with the target diagnosis:

- **MMSE**: Mini-Mental State Examination score  
- **Functional Assessment**  
- **Memory Complaints**  
- **Behavioral Problems**  
- **ADL**: Activities of Daily Living

---

## 🤖 Machine Learning Models

### Baseline Models
| Model | Accuracy | Notes |
|-------|----------|-------|
| KNN | 0.96 | Best baseline performance |
| Logistic Regression | 0.85 | Lower recall for positive class |
| Decision Tree | 0.94 | Competitive, but less stable |

KNN showed the highest accuracy, precision, and recall among baseline models.

---

### Ensemble Models
| Model | Accuracy | Precision | Recall | Comments |
|-------|----------|-----------|--------|-----------|
| Logistic Regression + Bagging | 0.858 | - | - | |
| Logistic Regression + Pasting | 0.958 | - | - | |
| Random Forest | 0.86 | 0.97 (1) | 0.94 (1) | Robust & easy to tune |
| Gradient Boosting | 0.965 | 0.97 (1) | 0.94 (1) | Best CV score |
| AdaBoost | 0.965 | 0.97 (1) | 0.94 (1) | Competitive |

- **Best Performing Models**: **Random Forest** and **Gradient Boosting** both achieved **96.5% test accuracy**.  
- Gradient Boosting had a slightly higher cross-validation score (95.35% vs 95.17%).  
- Random Forest is more robust and easier to tune for production.

---

## 📊 Key Findings

- Clinical and symptom data **can accurately predict Alzheimer’s diagnosis** with ML models.
- Ensemble models (Random Forest & Gradient Boosting) outperform simple classifiers.
- MMSE and ADL scores are particularly **important predictors**.
- Class imbalance and dataset size may impact generalization in broader use cases.

---

## ⚠️ Limitations & Future Work

- The dataset is relatively small and may not generalize well to all populations.  
- Potential class imbalance should be addressed with resampling or weighting techniques.  
- Future improvements:
  - Collect more diverse and balanced data.
  - Experiment with advanced models (e.g., Neural Networks).
  - Integrate explainable AI (XAI) methods to aid clinical interpretability.

---

## 🧰 Tech Stack

- **Language**: Python  
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`  
- **Models**: KNN, Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, AdaBoost  
- **Tools**: Jupyter Notebook

---

## 🛠️ How to Run

```bash
# Clone the repository

# Install dependencies

# Launch notebook for exploration and model training

📁 Repository Structure

Copy code
.
├── data/
│   ├── raw/                # Original dataset
│   └── processed/          # Cleaned data
├── notebooks/
│   ├── EDA.ipynb           # Exploratory data analysis
│   └── modeling.ipynb      # Model training and evaluation
├── src/
│   ├── train.py
│   └── utils.py
├── outputs/
│   ├── models/
│   ├── figures/
│   └── metrics/
├── presentation/
│   └── final_presentation.pdf
├── requirements.txt
└── README.md
👥 Team
    
    Julia
    Kinga
    Rafael
    Joma

Cohort: DATA-FT-Sept-2025

📜 License & Acknowledgments
Dataset from Kaggle — Rabie El Kharoua

Developed as part of DATA-FT-Sept-2025 ML Sprint

Licensed under the MIT License




Demographics Information 

Age: The age of the patients ranges from 60 to 90 years. 

Gender:   

0 = Male  

1 = Female. 

Ethnicity: The ethnicity of the patients, coded as follows: 

0: Caucasian 

1: African American 

2: Asian 

3: Other 

EducationLevel: The education level of the patients, coded as follows: 

0: None 

1: High School 

2: Bachelor's 

3: Higher 

Lifestyle Factors 

BMI: Body Mass Index of the patients 

ranging from 15 to 40. 

 
Smoking: Smoking status 

0 = No  

1 = Yes 

 
AlcoholConsumption: Weekly alcohol consumption in units 

ranging from 0 to 20. 
 

PhysicalActivity: Weekly physical activity in hours 

 ranging from 0 to 10. 


DietQuality: Diet quality score 

ranging from 0 to 10. 


SleepQuality:  Sleep quality score: 

ranging from 4 to 10. 

 
Medical History 

FamilyHistoryAlzheimers: Family history of Alzheimer's Disease 

0 = No  

1 = Yes 


CardiovascularDisease: Presence of cardiovascular disease, 

0 = No  

1 = Yes 


Diabetes: Presence of diabetes 

0 = No  

1 = Yes 


Depression: Presence of depression 

0 = No  

1 = Yes 


HeadInjury: History of head injury 

0 = No  

1 = Yes 


Hypertension: Presence of hypertension 

0 = No  

1 = Yes 

Clinical Measurements 

SystolicBP: Systolic blood pressure 

ranging from 90 to 180 mmHg. 


DiastolicBP: Diastolic blood pressure, 

ranging from 60 to 120 mmHg. 


CholesterolTotal: Total cholesterol levels 

ranging from 150 to 300 mg/dL. 


CholesterolLDL: Low-density lipoprotein cholesterol levels 

 ranging from 50 to 200 mg/dL. 

CholesterolHDL: High-density lipoprotein cholesterol levels 

ranging from 20 to 100 mg/dL. 

 
CholesterolTriglycerides: Triglycerides levels 

 ranging from 50 to 400 mg/dL. 

Cognitive and Functional Assessments 

 MMSE: Mini-Mental State Examination score 

ranging from 0 to 30.  

Lower scores indicate cognitive impairment. 


FunctionalAssessment: Functional assessment score, 

ranging from 0 to 10. 

 Lower scores indicate greater impairment. 

 
MemoryComplaints: Presence of memory complaints 

0 = No  

1 = Yes 

 
BehavioralProblems: Presence of behavioral problems 

0 = No  

1 = Yes 

 
ADL: Activities of Daily Living score 

ranging from 0 to 10.  

Lower scores indicate greater impairment. 


Symptoms 

Confusion: Presence of confusion 

0 = No  

1 = Yes 
 

Disorientation: Presence of disorientation, 

0 = No  

1 = Yes 
 

PersonalityChanges: Presence of personality changes, 

0 = No  

1 = Yes 
 

DifficultyCompletingTasks: Presence of difficulty completing tasks 

0 = No  

1 = Yes 
 

Forgetfulness: Presence of forgetfulness, 

0 = No  

1 = Yes 
 

Diagnosis Information 

Diagnosis: Diagnosis status for Alzheimer's Disease 

0 = No  

1 = Yes 

 