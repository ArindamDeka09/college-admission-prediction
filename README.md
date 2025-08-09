# College Admission Prediction

Predict the **Chance of Admit** for graduate applicants using classical machine learning models (**Linear Regression**, **Ridge Regression**, **Random Forest**).  
Built for students, admission consultants, and data enthusiasts to explore how profile features drive admission likelihood.

**Inputs:** GRE Score, TOEFL Score, University Rating, SOP, LOR, CGPA, Research  
**Output:** Chance of Admit (0–1)  

**Engineered Feature:**  
```
Profile_Strength = (GRE + TOEFL + 10×CGPA) / 3
```

---

## Table of Contents
- [Introduction / Motivation](#introduction--motivation)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements / Credits](#acknowledgements--credits)
- [Contact / Support](#contact--support)

---

## Introduction / Motivation
Graduate admissions are competitive and often opaque.  
This project uses supervised learning to estimate the probability of admission based on academic and profile variables.

**Problem it solves:**
- Provides an interpretable baseline to estimate Chance of Admit.
- Shows how different features and models influence outcomes.

**Key highlights:**
- Clean, reproducible notebook workflow (**ETL → Feature Engineering → Modeling → Evaluation**)
- Models compared: Linear Regression, Ridge Regression, Random Forest Regressor
- Metrics: **Mean Squared Error (MSE)** and **R²** on a held-out test set
- Simple feature engineering with `Profile_Strength` for intuitive signal

---

## Features
- Data checks (nulls, column cleanup)
- Feature engineering (`Profile_Strength`)
- Model training with **scikit-learn**:
  - Linear Regression
  - Ridge Regression
  - Random Forest Regressor
- Example evaluation results:
  ```
  Linear Regression: MSE ~ 0.0046, R² ~ 0.823
  Ridge Regression:  MSE ~ 0.0046, R² ~ 0.821
  Random Forest:     MSE ~ 0.0048, R² ~ 0.814
  ```

---

## Dataset
**Expected columns:**
```
Serial No., GRE Score, TOEFL Score, University Rating, SOP, LOR, CGPA, Research, Chance of Admit
```

**Note:**  
The notebook currently reads an Excel file from a local Windows path:
```
C:\Users\MY PC\OneDrive\Documents\New_Admission_Predict.csv.xlsx
```
If this repo is forked/cloned, change the `file_path` in the notebook to match a local dataset location, or place the dataset inside the repo (`data/New_Admission_Predict.csv.xlsx`) and update the path.

---

## Project Structure
```
College-Admission-Prediction-1.ipynb  → main Jupyter notebook
README.md                             → project documentation
data/                                 → dataset files (optional)
src/                                  → modularized scripts (optional)
reports/                              → figures/exports (optional)
```

---

## Installation
**Prerequisites:**
- Python 3.8+
- pip (or conda)
- Jupyter Notebook/Lab

**Create and activate a virtual environment (recommended):**
```bash
python -m venv .venv

# Linux/Mac
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

**Install dependencies:**
```bash
pip install -U pip
pip install jupyter pandas numpy scikit-learn seaborn matplotlib openpyxl
```

**Launch Jupyter:**
```bash
jupyter notebook
```
Then open `College-Admission-Prediction-1.ipynb`.

---

## Usage
1. Ensure your dataset is available locally.  
   Example (current absolute path):
   ```python
   file_path = r"C:\Users\MY PC\OneDrive\Documents\New_Admission_Predict.csv.xlsx"
   ```
   Or repo-relative path for portability:
   ```python
   file_path = "data/New_Admission_Predict.csv.xlsx"
   ```
2. Run notebook cells sequentially:  
   **Imports → Load/Clean → Feature Engineering → Train/Test Split → Train Models → Evaluate**
3. Review printed metrics and extend with plots or interpretability methods.

---

## Configuration
- **File path:** Edit `file_path` in the notebook.
- **Random seeds:** Add `random_state` for reproducibility.
- **Hyperparameters:** Tune Ridge `alpha` or Random Forest `max_depth` / `n_estimators`.

---

## Results
- Strong linear baselines (**R² ~ 0.82**)
- `Profile_Strength` effectively summarizes exam + CGPA signal
- Random Forest performed slightly below linear models on this dataset

**Ideas to improve:**
- Cross-validation and hyperparameter search
- SHAP/permutation importance for interpretability
- Outlier analysis and scaling
- Additional domain-specific features

---

## Contributing
1. Fork the repo and create a feature branch.
2. Follow **PEP8** and add docstrings/comments.
3. Include notes, results, and tests where relevant.
4. Open a pull request describing changes and motivation.

---

## License
MIT License (recommended). Add a `LICENSE` file to the repository.

---

## Acknowledgements / Credits
- Completed during a Data Science and AI training program at **Internselite**
- Mentor: **Ayush Srivastava**
- Libraries: pandas, numpy, scikit-learn, seaborn, matplotlib, openpyxl

---

## Contact / Support
- **Author:** Arindam Deka  
- **Email:**  arindamdeka001@gmail.com  
- **GitHub:** ArindamDeka09
- **Issues:** Please open an issue with details and steps to reproduce
