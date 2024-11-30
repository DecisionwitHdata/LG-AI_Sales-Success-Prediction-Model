# Sales Success Prediction Model

## 📋 Project Overview
This project aims to develop machine learning models to predict sales success. Through various experiments with different models and optimization techniques, we achieved significant improvements in prediction performance.

## 🔬 Experiments & Results
| Experiments | Code | Score |
|------------|------|---------|
| Decision Tree | [Decision_Tree.ipynb](experiments/Decision_Tree.ipynb) | 0.5751 |
| Ensemble | [Ensemble_0.5751.ipynb](experiments/Ensemble_0.5751.ipynb) | 0.5751 |
| XGBClassifier & Optuna | [XGBClassifier&Optuna_0.597.ipynb](experiments/XGBClassifier&Optuna_0.597.ipynb) | 0.5922 |
| Optuna2 | [Optuna2_0.597.ipynb](experiments/Optuna2_0.597.ipynb) | 0.597 |
| XGBClassifier | [XGBClassifier_0.601.ipynb](experiments/XGBClassifier_0.601.ipynb) | 0.601 |
| Ensemble & Optuna | [Ensemble&Optuna_0.5922.ipynb](experiments/Ensemble&Optuna_0.5922.ipynb) | 0.5922 |
| Final Model | [Final_0.62.ipynb](final/Final_0.62.ipynb) | 0.62 |

## 🛠 Data Processing & Feature Engineering

### Data Preprocessing Steps
1. **Label Encoding** for categorical variables:
  - customer_country
  - business_area
  - business_unit
  - customer_type
  - enterprise
  - customer_job
  - inquiry_type
  - product_category
  - and more...

2. **Missing Value Treatment**
  - Numerical columns: Filled with median values
  - Categorical columns: Filled with 'missing'
  - Strategic variables (id, it, idit): Filled with 0
  - com_reg_ver_win_rate: Median value
  - ver_win_rate_x: Median value
  - ver_win_ratio_per_bu: Median value

3. **Feature Selection**
  - Removed columns: id_strategic_ver, it_strategic_ver, idit_strategic_ver, lead_desc_length
  - Dropped: customer_type, historical_existing_cnt, product_subcategory, product_modelname
  - Removed: expected_timeline, business_subarea

4. **Imbalanced Data Handling**
  - Retained all positive samples (is_converted = 1)
  - Undersampled negative cases to 25,000 samples

## 🤖 Model Development

### 1. Base Models
- Decision Tree Classifier (Score: 0.5751)
- XGBClassifier (Score: 0.601)
- Ensemble Models (Score: 0.5751 ~ 0.5922)

### 2. Advanced Approaches
- **Ensemble Strategy**
 - Combined multiple models with weighted voting
 - Weights distribution: [0.1, 0.1, 0.1, 1.2]
 - Models included:
   - LogisticRegression
   - RandomForestClassifier
   - GradientBoostingClassifier
   - XGBClassifier

- **Hyperparameter Optimization**
 - Utilized Optuna for automated parameter tuning
 - Optimized parameters for each base model
 - Enhanced ensemble performance through optimal weights

### 3. Final Model (Score: 0.62)
- Best performing model combining all optimizations
- Achieved through careful feature selection and model tuning

