# 🌍 CO₂ Emissions Predictor — Polynomial Regression Dashboard

An interactive machine learning dashboard built with **Streamlit** to predict CO₂ emissions using energy consumption, renewable energy percentage, and GDP. The application uses **Polynomial Regression** and provides data exploration, model evaluation, interactive predictions, and downloadable results.

## 📌 Project Overview

CO₂ emissions are influenced by several economic and energy-related factors. This project explores the relationship between these factors and CO₂ emissions using a polynomial regression model.

Users can upload a sustainability dataset, explore its statistical properties, evaluate model performance, experiment with different input values, and download predictions and the trained model.

## ✨ Features

- **Dataset Upload:** Upload a CSV file containing sustainability data.
- **Data Preview:** View dataset records, summary statistics, and training/testing data counts.
- **Data Cleaning:** Automatically remove rows containing missing values.
- **Exploratory Data Analysis:** Visualize feature correlations, feature relationships, and data distributions.
- **Polynomial Regression:** Train a regression model with a configurable polynomial degree from 1 to 5.
- **Model Evaluation:** View Mean Squared Error (MSE), R² score, actual-versus-predicted values, and residual plots.
- **Interactive Predictions:** Adjust energy consumption, renewable energy percentage, and GDP to estimate CO₂ emissions.
- **Sensitivity Analysis:** Explore how predicted emissions change when one feature varies while the others remain constant.
- **Model Download:** Download the trained model and polynomial feature transformer as a `.pkl` file.
- **Prediction Export:** Download test-set predictions as a CSV file.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Interactive web dashboard |
| Pandas | Data loading and manipulation |
| NumPy | Numerical computations |
| Scikit-learn | Polynomial feature transformation, regression, and evaluation |
| Plotly Express | Interactive data visualizations |
| Plotly Graph Objects | Additional performance plots |
| Statsmodels | Listed dependency for statistical analysis and regression plotting support |
| Joblib | Saving and loading serialized machine learning objects |

## 📊 Dataset Requirements

The application expects a CSV dataset named `sustainability_data.csv`.

The dataset must contain the following columns:

| Column | Description |
|---|---|
| `Energy_Consumption` | Energy consumption value |
| `Renewable_Percentage` | Percentage of renewable energy |
| `GDP` | Gross Domestic Product value |
| `CO2_Emissions` | Target variable used to train and evaluate the model |

The first three columns are the input features, and `CO2_Emissions` is the target variable.

**Important:** The application uses the dataset's actual values and does not specify particular units or a geographic coverage. Ensure the uploaded dataset has suitable numerical values for all required columns.

## 📁 Project Structure

```text
CO2-Emissions-Predictor/
│
├── app.py
├── requirements.txt
├── sustainability_data.csv
├── polynomialRegModel.pkl
└── README.md
```

- `app.py` — Streamlit dashboard and machine learning workflow.
- `requirements.txt` — Python package dependencies.
- `sustainability_data.csv` — Dataset used by default when available.
- `polynomialRegModel.pkl` — Existing serialized model file.
- `README.md` — Project documentation.

*The dataset filename and folder structure above assume the CSV is included in the project. If it is not, users can upload a compatible CSV through the dashboard.*

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd CO2-Emissions-Predictor
```

Replace `<your-github-repository-url>` with your actual repository URL.

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Place `sustainability_data.csv` in the same directory as `app.py`, or upload the CSV using the dashboard's sidebar.

Make sure the file includes all four required columns.

### 5. Run the application

```bash
streamlit run app.py
```

Streamlit will display a local URL, usually `http://localhost:8501`. Open it in your browser to access the dashboard.

## 🧠 Machine Learning Workflow

1. Load the sustainability dataset from the uploaded CSV or default file.
2. Validate the required columns and remove rows with missing values.
3. Separate the input features and target variable.
4. Split the data into training and testing sets.
5. Transform the input features using `PolynomialFeatures`.
6. Train a `LinearRegression` model on the transformed features.
7. Generate predictions for the test set.
8. Evaluate performance using MSE and R².
9. Use the trained pipeline components to predict emissions for user-selected inputs.

### Model Configuration

Users can adjust the following settings in the sidebar:

- **Polynomial Degree:** 1–5, with a default of 2.
- **Test Set Size:** 10%–50%, with a default of 20%.
- **Random State:** Controls reproducibility of the train-test split, with a default of 42.

## 📈 Dashboard Sections

| Section | Functionality |
|---|---|
| Data | Dataset preview, row counts, and summary statistics |
| Explore | Correlation heatmap, scatter plots, and distributions |
| Model Performance | MSE, R², actual-versus-predicted plot, and residual analysis |
| Predict | Interactive CO₂ emissions predictions and sensitivity analysis |
| Download | Export the model and test-set predictions |

## 💾 Downloadable Outputs

The dashboard provides two downloadable files:

- `polynomialRegModel.pkl` — Contains the fitted regression model, polynomial transformer, and feature names.
- `test_predictions.csv` — Contains the test-set input features, actual CO₂ emissions, and predicted CO₂ emissions.

The `.pkl` file is created from the model trained during the current application run. The existing `polynomialRegModel.pkl` file is not automatically loaded by the supplied code.

## 🔮 Future Enhancements

- Add model comparison with other regression algorithms.
- Improve input validation and error handling for invalid or insufficient datasets.
- Include additional sustainability indicators where suitable data is available.
- Add model persistence and loading for previously trained models.
- Deploy the dashboard to a cloud hosting platform.

## 👩‍💻 Author

**Vidhya Sri A J**

Computer Science and Engineering Student

---

*This project demonstrates data preprocessing, polynomial regression, model evaluation, exploratory data analysis, and interactive machine learning application development using Python.*
