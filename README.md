# ✈️ Flight Delay Prediction with Time Features and Cyclical Encoding

## 📌 Project Overview
This project focuses on **predicting flight delays** using advanced time-based feature engineering and cyclical encoding techniques to capture periodic patterns in flight data.

- 🔍 **Comprehensive Time Analysis** – exploring delay patterns across hours, days, and time periods
- 🛠 **Cyclical Encoding** – implementing sine/cosine transformations for temporal features
- 📊 **Feature Engineering** – creating airline performance metrics, route analysis, and airport congestion features
- 🤖 **Multi-Model Comparison** – evaluating Random Forest, Gradient Boosting, and Logistic Regression
- 🎯 **Goal** – build accurate flight delay prediction models that understand temporal patterns and operational factors

## 📊 Dataset

The dataset (`Airlines.csv`) contains flight records with the following features:

- **Airline**: Name of the airline operating the flight
- **Flight**: Flight number identifier
- **AirportFrom**: Departure airport code
- **AirportTo**: Arrival airport code  
- **DayOfWeek**: Day of the week (1-7, Monday to Sunday)
- **Time**: Departure time in minutes from midnight (0-1439)
- **Length**: Flight duration in minutes
- **Delay**: Flight delay status (0 = No Delay, 1 = Delayed) - target variable

**Dataset Statistics:**
- 539,383 total flight records
- Balanced distribution with ~44.7% delayed flights
- Multiple airlines and airport routes represented

---

## 🔧 Key Techniques Implemented

### 1. Data Exploration & Visualization

- **Target Distribution Analysis**: Bar and pie charts showing delay vs on-time flight proportions
- **Time-Based Pattern Discovery**: 6-panel visualization dashboard revealing:
  - Hourly delay patterns throughout the day
  - Day-of-week delay variations  
  - Time period analysis (Morning, Afternoon, Evening, Night)
  - Airline performance ranking
  - Flight length distribution by delay status
  - Weekday vs weekend delay patterns
- **Key Insights**: Evening flights show highest delay rates, with cascading delays throughout the day

- ### 2. Time-Based Feature Extraction

- **Hour Extraction**: Converting time to 24-hour format (0-23)
- **Minute Extraction**: Extracting minute component for granular time analysis
- **Time Period Categorization**: Grouping flights into meaningful periods:
  - Morning (5:00-11:59)
  - Afternoon (12:00-16:59) 
  - Evening (17:00-20:59)
  - Night (21:00-4:59)
- **Day Type Classification**: Weekday vs Weekend categorization for operational pattern analysis

### 3. Cyclical Encoding Implementation

**🌟 Core Innovation**: Transforming linear time features into cyclical coordinates

- **Mathematical Foundation**: Using sine and cosine transformations:
  ```
  sin_feature = sin(2π × value / max_value)
  cos_feature = cos(2π × value / max_value)
  ```
- **Applied to Multiple Time Dimensions**:
  - Hour cyclical encoding (24-hour cycle)
  - Day of week cyclical encoding (7-day cycle)
  - Minute cyclical encoding (60-minute cycle)
- **Key Benefits**:
  - Hour 23 and Hour 0 are mathematically close
  - Sunday and Monday maintain proper temporal relationship
  - Models can learn periodic patterns effectively
- **Visualization**: Dual-plot showing sine/cosine waves for each time dimension

### 4. Advanced Feature Engineering

- **Categorical Encoding**: Label encoding for airlines, airports, and time periods
- **Route Analysis**: 
  - Unique route identification (AirportFrom_AirportTo)
  - Route-specific delay rate calculation
- **Airline Performance Metrics**: Historical delay rates per airline
- **Airport Congestion Features**: Hourly flight volume per departure airport
- **Feature Integration**: Merging engineered features with original dataset

### 5. Model Training & Comprehensive Evaluation

- **Multi-Algorithm Approach**:
  - **Random Forest**: Ensemble of 100 decision trees with parallel processing
  - **Gradient Boosting**: Sequential 100-stage boosting algorithm
  - **Logistic Regression**: Linear model with feature scaling
- **Smart Data Handling**: 
  - Scaled features for Logistic Regression
  - Original features for tree-based models
- **Performance Metrics**:
  - Accuracy, Precision, Recall, F1-Score
  - Confusion matrices for detailed error analysis
  - Model comparison dashboard
- **Train-Test Split**: 80-20 split with stratification to maintain delay distribution

---

## 🏆 Results

The models achieved the following performance on the test set:

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|---------|----------|
| **Gradient Boosting** | **66.32%** | **66.30%** | **49.61%** | **56.75%** |
| Logistic Regression | 65.72% | 64.97% | 50.02% | 56.52% |
| Random Forest | 61.83% | 57.41% | 55.45% | 56.41% |


**🥇 Best Model: Gradient Boosting**
- Optimal balance between precision and recall
- Fewest false alarms while maintaining delay detection capability
- Superior handling of feature interactions

### Key Findings:

- **Time Patterns**: Evening flights (17:00-21:00) show significantly higher delay rates
- **Cyclical Encoding Impact**: Enabled models to understand that late-night and early-morning flights share similar operational characteristics
- **Airline Performance**: Clear performance differences between airlines, with delay rates varying by 10-20%
- **Route Sensitivity**: Specific airport pairs show consistently higher delay patterns
- **Weekend Effect**: Weekends show different delay patterns compared to weekdays


### Business Impact:
- **Operational Planning**: Airlines can adjust staffing and resources based on predicted high-delay periods
- **Passenger Experience**: Proactive communication for likely delayed flights
- **Resource Optimization**: Better gate management and crew scheduling
- **Revenue Protection**: Reduced compensation costs through improved delay management

---

## 💻 Requirements

```
Python 3.8+
pandas >= 1.3.0
numpy >= 1.20.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
scikit-learn >= 1.0.0
```

---


