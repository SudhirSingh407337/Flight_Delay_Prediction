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
