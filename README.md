# 🏥 Pusula Talent Academy - Data Science Intern Case Study

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BerivanAyaz/Pusula_Berivan_Ayaz/blob/main/Pusula_Case_Study.ipynb)

**Author:** Berivan Ayaz  
**Email:** berivannayaz@gmail.com  

---

## 1. Project Overview

This project involves a comprehensive Exploratory Data Analysis (EDA) and Data Pre-processing of a physical medicine & rehabilitation dataset provided by Pusula Talent Academy. The dataset consists of 2,235 initial observations and 13 features.

The primary goal of this case study is **not to build a predictive model**, but to clean, transform, and structure raw healthcare data into a model-ready format. The defined target variable for potential modeling is `TedaviSuresi` (Treatment Duration).

---

## 2. Project Workflow & Key Steps

### Phase 1: Exploratory Data Analysis (EDA)
* **Data Loading & Health Check:** Loaded the raw Excel data, inspected its shape, data types, and quantified missing values.
* **Visual Analysis:** Evaluated distributions of key features like `Yas` (Age), `Cinsiyet` (Gender), and the target variable `TedaviSuresi`.
* **Deep Dive into Complex Columns:** Parsed high-cardinality, multi-value text columns (`KronikHastalik`, `Tanilar`) to identify frequencies and inconsistencies.
* **Bivariate Analysis:** Investigated the relationship between chronic conditions and treatment duration, identifying standardized protocol influences.

### Phase 2: Data Pre-processing & Feature Engineering
* **Text Normalization:** Standardized text data (lowercase, whitespace stripping, and handling special Turkish characters).
* **Smart Deduplication:** Implemented a robust deduplication strategy to resolve duplicated treatment updates and retain unique, up-to-date patient treatment plans.
* **Feature Engineering:** 
  * Created aggregated features like `ToplamUygulamaSuresi` (Total Application Duration).
  * Generated dynamic binary (1/0) flags for frequent categories in complex columns (`KronikHastalik`, `Alerji`).
* **Imputation & Encoding:** Handled missing values via statistical mode/placeholders and applied One-Hot Encoding to categorical features (`Cinsiyet`, `KanGrubu`, `Uyruk`).

---

## 💡 Key Insights & Findings (Summary)
* **Data Quality:** The raw dataset contained ~41% exact duplicate rows, highlighting the critical need for a custom deduplication pipeline in healthcare operational datasets.
* **Missing Data Handling:** Allergies and Blood Groups had high missing rates (~42% and ~30%), which were systematically handled to prevent information loss without biasing the core targets.
* **Standardization:** Healthcare procedures showed strict protocol adherence, where specific diagnoses heavily dictated the length of treatment sessions.

---

## 3. Repository Structure
```text
├── Pusula_Case_Study.ipynb         # Main Jupyter Notebook containing full EDA & Preprocessing
├── requirements.txt                # Required Python packages
└── README.md                       # Project documentation

---

## 4. How to Run the Code
To replicate the results, follow these steps:
* **Clone the Repository:** git clone [https://github.com/BerivanAyaz/Pusula_Berivan_Ayaz.git](https://github.com/BerivanAyaz/Pusula_Berivan_Ayaz.git)
* **Set up the Data:** Download the dataset (Talent_Academy_Case_DT_2025.xlsx). Upload it to your Google Drive inside a folder named pusula.
* **Open in Google Colab:** Click the "Open in Colab" badge at the top of this file or upload Pusula_Case_Study.ipynb to Colab.
* **Update File Path (if needed):** Ensure the file path matches your Google Drive directory: file_path = '/content/drive/MyDrive/pusula/Talent_Academy_Case_DT_2025.xlsx'
* **Run the Notebook:** Execute cells sequentially from top to bottom. 
