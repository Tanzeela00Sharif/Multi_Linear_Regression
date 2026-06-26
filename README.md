# Multi_Linear_Regression
# 🏠 Housing Price Prediction - Multiple Linear Regression

## 📌 Project Overview
This project builds a **Multiple Linear Regression** model to predict house prices based on various property features such as area, number of bedrooms, bathrooms, and amenities like air conditioning and parking.

## 📊 Dataset
The dataset (`Housing.csv`) contains **545 records** with **13 columns**:

| Column | Description |
|---|---|
| `price` | Price of the house (target variable) |
| `area` | Area of the house (sq. ft.) |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `stories` | Number of stories |
| `mainroad` | Connected to main road (yes/no) |
| `guestroom` | Has guest room (yes/no) |
| `basement` | Has basement (yes/no) |
| `hotwaterheating` | Has hot water heating (yes/no) |
| `airconditioning` | Has air conditioning (yes/no) |
| `parking` | Number of parking spaces |
| `prefarea` | Located in preferred area (yes/no) |
| `furnishingstatus` | Furnished / Semi-furnished / Unfurnished |

## ⚙️ Data Preprocessing
1. **Categorical encoding:**
   - Binary columns (`mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `prefarea`) mapped to `1`/`0`.
   - `furnishingstatus` converted using **one-hot encoding** (`pd.get_dummies`, `drop_first=True`) to avoid the dummy variable trap.
2. **Train-test split:** 80% training data, 20% test data (`random_state=42` for reproducibility).

## 🧠 Model
- **Algorithm:** Multiple Linear Regression (`sklearn.linear_model.LinearRegression`)
- **Features used:** All available columns after encoding
- **Target:** `price`

## 📈 Results

| Metric | Value |
|---|---|
| **R² Score** | 0.59 |
| **MSE** | 828,620.88 |
| **RMSE** | ~910 |

### Interpretation
- The model explains approximately **59% of the variance** in house prices.
- The remaining variation is likely due to:
  - Non-linear relationships between features and price
  - Missing real-world factors (exact location, build quality, market trends)
  - Presence of outliers in price/area
- This is a **fair baseline result** for a linear model on this type of dataset.

## 🔍 Future Improvements
- [ ] Detect and remove outliers (IQR method)
- [ ] Apply feature scaling (`StandardScaler`)
- [ ] Try non-linear models (Random Forest, Gradient Boosting) for comparison
- [ ] Perform feature selection / importance analysis
- [ ] Hyperparameter tuning for ensemble models

## 🛠️ Tech Stack
- Python
- Pandas, NumPy
- Matplotlib / Seaborn
- Scikit-learn

## 🚀 How to Run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
python housing_price_model.py
```

## 📁 Project Structure
