# 🍷 Beverage Quality Classification with Random Forest

This project uses Random Forest and Decision Tree classifiers to predict beverage quality based on physicochemical properties.

## 📂 Dataset
- `Beverage.csv`: 4898 observations
- 11 numerical features and 1 categorical target (`quality`)
- Target converted into binary:
  - `Excellent` → 1
  - Others → 0

## ⚙️ Methodology
1. **Data Preprocessing**:
   - Conversion of target variable
   - One-hot encoding of key features (`alcohol`, `volatile acidity`, `sulphates`)
   - Standardization using `StandardScaler`
   - Class balancing using **SMOTE**

2. **Modeling**:
   - **Decision Tree** with `entropy` criterion
   - **Random Forest** with hyperparameter tuning via `GridSearchCV`
   - Evaluation using:
     - Accuracy
     - Confusion Matrix
     - Cross-validation

3. **Dimensionality Reduction**:
   - PCA with 2 components
   - Explained variance ≈ 1.89%

4. **Clustering**:
   - KMeans with Elbow method
   - Optimal clusters: **4**
   - PCA projection used for visualizing clusters

## 📊 Model Results

| Model            | Accuracy | TP  | TN  | FP  | FN  |
|------------------|----------|-----|-----|-----|-----|
| Decision Tree    | 0.715    | 215 | 836 | 319 | 100 |
| Random Forest    | 0.883    | 211 | 1087|  68 | 104 |
| Random Forest Tuning | 0.881 | 209 | 1086|  69 | 106 |

> Best hyperparameters: `max_depth=30`, `n_estimators=450`

## 🔍 Feature Importance (Random Forest)
Top predictors:
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Required packages (see `requirements.txt`)

### Installation
1. Clone the repository
   ```bash
   git clone https://github.com/your-username/python_data_analysis.git
   cd python_data_analysis/random_forest_example
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   .\\venv\\Scripts\\activate  # Windows
   source venv/bin/activate  # macOS/Linux
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Usage
1. Place your `Beverage.csv` in the project root directory
2. Run the analysis:
   ```bash
   python random_forest_baverages.py
   ```

## 📂 Project Structure
```
random_forest_example/
├── random_forest_baverages.py  # Main analysis script
├── requirements.txt           # Python dependencies
└── README.md                 # This file
```

## 📝 License
This project is licensed under the MIT License.
