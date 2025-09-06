# Pusula Talent Academy - Data Science Intern Case Study

**Name Surname:** Berivan Ayaz
**Email:** berivannayaz@gmail.com

---

## 1. Project Overview

This project involves a comprehensive Exploratory Data Analysis (EDA) and Data Pre-processing of a physical medicine & rehabilitation dataset provided by Pusula Talent Academy. The dataset consists of 2235 initial observations and 13 features.

The primary goal of this case study is **not to build a predictive model**, but to clean, transform, and structure the raw data into a model-ready format. The defined target variable for potential modeling is `TedaviSuresi`.

The entire process is documented in the `Pusula_Case_Study.ipynb` Jupyter Notebook and follows a structured workflow from data loading to final feature engineering.

## 2. Project Workflow & Key Steps

The project was executed in a step-by-step manner, with each logical step preserved in a separate cell within the notebook for clarity and reproducibility.

### Phase 1: Exploratory Data Analysis (EDA)
- **Data Loading & Health Check:** The raw Excel data was loaded, and an initial analysis was performed to understand its shape, data types, and missing values.
- **Visual Analysis:** Key features like `Yas` (Age), `Cinsiyet` (Gender), and the target variable `TedaviSuresi` were visualized to understand their distributions.
- **Deep Dive into Complex Columns:** High-cardinality, multi-value columns like `KronikHastalik` (Chronic Diseases) and `Tanilar` (Diagnoses) were parsed to identify the most frequent entries and uncover data quality issues such as inconsistent text formatting.
- **Bivariate Analysis:** The relationship between top chronic diseases and the target variable was investigated, revealing that standardized treatment protocols heavily influence the treatment duration.

### Phase 2: Data Pre-processing
- **Text Normalization:** All textual data was standardized using techniques like converting to lowercase, stripping whitespace, and handling special Turkish characters (e.g., 'i̇' vs. 'i') to ensure data consistency.
- **Data Consolidation & Smart Deduplication:** A detailed analysis revealed that multiple rows often represented a single, updated treatment plan. A robust, multi-step deduplication strategy was implemented to consolidate patient information and retain only the most up-to-date record for each unique treatment plan. This reduced the dataset to its core analysis unit: the treatment plan.
- **Feature Engineering:**
  - **Aggregated Features:** New features like `ToplamUygulamaSuresi` (Total Application Duration) were created from granular data before deduplication.
  - **Dynamic Binary Features:** Binary (1/0) features were created for the most significant entries in complex columns like `KronikHastalik` and `Alerji`.
- **Imputation:** All remaining missing values (`NaN`) and empty strings were handled using appropriate strategies (mode for categorical, 'yok' for empty strings).
- **One-Hot Encoding:** Low-cardinality categorical columns (`Cinsiyet`, `KanGrubu`, `Uyruk`) were converted into a numerical format using one-hot encoding.
- **Final Cleanup:** All redundant and non-predictive columns were dropped to produce the final, model-ready dataset.

## 3. How to Run the Code

To replicate the results, please follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/BerivanAyaz/Pusula_Berivan_Ayaz.git
    ```
2.  **Set up the Data:**
    - Download the dataset (`Talent_Academy_Case_DT_2025.xlsx`).
    - Upload it to your Google Drive, preferably in a folder named `pusula`.
3.  **Open in Google Colab:**
    - Open the `Pusula_Case_Study.ipynb` notebook in Google Colab.
4.  **Update File Path:**
    - In the first code cell, update the `file_path` variable to match the location of the dataset in your Google Drive:
      ```python
      file_path = '/content/drive/MyDrive/pusula/Talent_Academy_Case_DT_2025.xlsx'
      ```
5.  **Run the Notebook:**
    - Execute the cells sequentially from top to bottom. The notebook is designed to be run in order, as each step builds upon the previous one.

## 4. Final Output

The final output of the notebook is the `df_final_features` DataFrame, which is a fully cleaned, imputed, and feature-engineered dataset ready for predictive modeling. All features in this final dataframe are numerical.```
