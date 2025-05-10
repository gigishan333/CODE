# NYC Airbnb Project - Data Analysis and Predictive Modeling

**Shan (Gigi) Gao**  
[LinkedIn Profile](https://www.linkedin.com/in/gigishanbu)

---
# NYC Airbnb Data Analysis & Price Prediction

![Python](https://img.shields.io/badge/Python-3.7%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Installation](#-installation)
- [Usage](#-usage)
- [Methodology](#-methodology)
- [Results](#-results)
- [Future Work](#-future-work)
- [Contributing](#-contributing)
- [License](#-license)

## 🏙 Project Overview
This project analyzes NYC Airbnb listings from 2023 to:
- Understand pricing patterns across neighborhoods
- Identify key factors influencing rental prices
- Build a predictive model for listing prices
- Provide actionable insights for hosts and travelers

## 📊 Dataset
**File:** `NYC-Airbnb-2023.csv`  
**Records:** 42,931 listings  
**Features:** 18 columns including:

| Feature Category | Example Fields |
|-----------------|----------------|
| Listing Info | `id`, `name`, `host_id` |
| Location | `neighbourhood_group`, `latitude` |
| Property Details | `room_type`, `price` |
| Availability | `minimum_nights`, `availability_365` |
| Reviews | `number_of_reviews`, `reviews_per_month` |

## ⚙️ Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/nyc-airbnb-analysis.git
   cd nyc-airbnb-analysis
2. Create and activate virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate    # Windows
3. Install dependencies:
   ```bash
   pip install -r requirements.txt

## 🚀 Usage
1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
2. Open NYC_Airbnb_Project.ipynb.

3. Run cells sequentially to:
- Load and explore the dataset
- Perform exploratory data analysis (EDA)
- Preprocess features and train machine learning models
- Evaluate model performance
- Generate visualizations

---

## 🔍 Methodology

### Data Preprocessing

```python
# Create preprocessing pipelines
numeric_transformer = Pipeline(steps=[
    ('imputer', SimpleImputer(strategy='median')),
    ('scaler', StandardScaler())
])

categorical_transformer = Pipeline(steps=[
    ('imputer', SimpleImputer(strategy='constant', fill_value='missing')),
    ('onehot', OneHotEncoder(handle_unknown='ignore'))
])
```

### Model Pipeline

```python
preprocessor = ColumnTransformer(
    transformers=[
        ('num', numeric_transformer, numeric_features),
        ('cat', categorical_transformer, categorical_features)
    ])

model = Pipeline(steps=[
    ('preprocessor', preprocessor),
    ('regressor', RandomForestRegressor(n_estimators=100))
])
```

---

## 📊 Model Evaluation

| Metric               | Score  |
|----------------------|--------|
| R² Score             | 0.72   |
| Mean Squared Error   | 1200   |
| Mean Absolute Error  | 28.5   |

---

## 📈 Results

### Key Insights

- **Price Distribution by Neighborhood**  
  Manhattan listings are generally priced higher than other boroughs.

  ```python
  plt.figure(figsize=(10,6))
  sns.boxplot(x='neighbourhood_group', y='price', data=df)
  plt.title('Price Distribution by Neighborhood')
  plt.show()
  ```

### Top Predictive Features

- Room type (Entire home/apt vs Private room)
- Neighborhood group (Manhattan is highest)
- Minimum nights requirement
- Availability throughout the year

---

## 🔮 Future Work

- Incorporate sentiment analysis of guest reviews
- Add time-series analysis of seasonal price fluctuations
- Develop an interactive dashboard with Plotly/Dash
- Include external datasets (e.g., crime rates, transportation access)

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the project  
2. Create your feature branch  
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. Commit your changes  
   ```bash
   git commit -m "Add some AmazingFeature"
   ```
4. Push to the branch  
   ```bash
   git push origin feature/AmazingFeature
   ```
5. Open a Pull Request

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

*Created with 🌟 using Python and Jupyter Notebook*  
**Data source:** [NYC Airbnb Open Data (2023)](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data)
