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
