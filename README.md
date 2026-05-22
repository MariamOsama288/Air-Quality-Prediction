# Air Quality Prediction 🌬️🧠

An Artificial Intelligence Deep Learning project developed to analyze environmental factors and predict pollution levels, specifically focusing on forecasting high carbon monoxide (CO) levels.

## 📝 Project Overview
Air pollution is a critical environmental and health challenge. This project leverages deep learning architectures to predict whether CO levels will exceed safe thresholds in the next hour, utilizing sensor data and historical data from the preceding 6 hours.

## 📊 Dataset Description
- **Source**: AirQualityUCI Dataset.
- **Size**: 9,824 entries with 15 columns of environmental attributes.
- **Features**: Includes hourly responses from gas sensors (CO, NOx, NO2, etc.) along with Temperature (T), Relative Humidity (RH), and Absolute Humidity (AH).

## 🛠️ Data Pre-Processing & Engineering
To ensure high model accuracy, the following pipeline was implemented:
- **Exploratory Data Analysis (EDA)**: Visualized target distributions, feature ranges, and missing values.
- **Data Cleaning**: Handled missing values via median/mode imputation and removed 467 duplicate rows.
- **Outlier Handling**: Capped extreme values at the 1.5*IQR boundaries across numeric features.
- **Feature Engineering**: Generated temporal difference features, squared features, and specific ratios (e.g., NOx/CO ratio) to capture complex relationships.
- **Sequence Creation**: Prepared sequential data with a sequence length of 6 hours to predict next-hour boundaries.

## 🧪 Deep Learning Models Evaluated
We built and compared three distinct Deep Learning architectures using TensorFlow/Keras:
1. **Simple RNN**: Evaluated recurrent behavioral patterns across sequential time windows.
2. **Artificial Neural Network (ANN)**: Built using flat features with Dense layers and Dropout for regularization.
3. **LSTM (Long Short-Term Memory)**: Implemented to robustly capture long-term dependencies in the air quality time-series dataset.

## 📈 Experimental Results & Comparison
After training for 40 epochs with Early Stopping callbacks, the model performance summary is as follows:


| Model Architecture | Overall Accuracy | F1-Score (Class 0) | F1-Score (Class 1) |
| :--- | :---: | :---: | :---: |
| **LSTM** 🏆 | **89%** | **0.93** | **0.79** |
| **RNN** | 86% | 0.91 | 0.76 |
| **ANN** | 83% | 0.87 | 0.72 |

*The **LSTM model achieved the highest performance**, proving its strength in handling sequential environmental data.*

## 👥 Team Members
Project developed by our AI Group under the supervision of **Dr. Heba Zaki**:
- Mariam Osama
- Seif Mohamed
- Darine Farrag
