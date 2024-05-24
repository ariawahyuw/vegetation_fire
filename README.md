
# Vegetation Fire Prediction

## Getting Started
To run the project, you need to install the required libraries using the following command:
```
pip install -r requirements.txt
```
## Usage
To see the results of the project, you can see it in the: `model.ipynb` file.

---

## Introduction
This project aims to predict vegetation fires in Kalimantan using machine learning models. The dataset used in this project is a combination of climate data and satellite data, which are from BMKG Indonesia and NASA MODIS C61. The project uses the FRP as the target variable and the climate data as the features. The project uses machine learning models to predict the occurrence of vegetation fires.

## Dataset
The dataset consists of two main dataframes, the climate data and the satellite data. The climate data consists of the following columns:
- date: the date of the data
- station_id: the station id
- Tx: maximum temperature
- Tn: minimum temperature
- Tavg: average temperature
- RH_avg: average relative humidity
- RR: rainfall
- ss: sunshine duration
- ff_x: maximum wind speed
- ff_avg: average wind speed
- ddd_x: maximum wind direction
- ddd_car: wind direction in cardinal direction

The satellite data consists of the following columns:
- latitude: the latitude of the fire
- longitude: the longitude of the fire
- date: the date of the data
- time: the time of the data
- frp: the fire radiative power

## Data Preprocessing
The data is preprocessed by removing missing values and filtering the data based on the following conditions:
- The temperature is greater than 17 degrees Celsius
- The wind speed is less than 17 m/s
- The sunshine duration is greater than 1 hour
- The wind direction is not 888

The data is then filtered based on the location of the fire, which is in Kalimantan. The data is then merged based on the station id and the date. The data is then split into training and testing data.

## Feature Selection
The feature selection is done using the following methods:
- Pearson Correlation
- Random Forest Feature Importance

The selected features are:
Tx, ff_avg, RH_avg, RR, ss

## Model Selection
The following models are used in this project:
- Decision Tree
- Logistic Regression
- Support Vector Machine
- K-Nearest Neighbors
- Random Forest
- Gradient Boosting

The models are trained using the training data and evaluated using the testing data. The best model is selected based on the objective function, which is a combination of the F2-score, precision, recall, and accuracy.

## Model Explanation
The best model is explained using rule-based explanation TE2Rules.
The rules are written in the <a href="rules/rules.txt">rules.txt</a> file. The rules explain the model's predictions and show the relationship between the features and the target variable.

## Results
### Training data
---
| Model | F2-score | Precision | Recall | Accuracy | Objective value |
| --- | --- | --- | --- | --- | --- |
| Decision Tree | 0.83 | 0.88 | 0.82 | 0.85 | 0.84 |
| Logistic Regression | 0.8 | 0.8 | 0.8 | 0.81 | 0.8 |
| Support Vector Machine | 0.86 | 0.88 | 0.86 | 0.88 | 0.87 |
| K-Nearest Neighbors | 0.94 | 0.91 | 0.95 | 0.93 | 0.94 |
| Random Forest | 0.88 | 0.9 | 0.87 | 0.89 | 0.88 |
| Gradient Boosting | 0.96 | 0.96 | 0.96 | 0.96 | 0.96 |

### Testing data
---
| Model | F2-score | Precision | Recall | Accuracy | Objective value |
| --- | --- | --- | --- | --- | --- |
| Decision Tree | 0.79 | 0.84 | 0.78 | 0.83 | 0.8 |
| Logistic Regression | 0.79 | 0.79 | 0.79 | 0.8 | 0.79 |
| Support Vector Machine | 0.84 | 0.86 | 0.83 | 0.86 | 0.84 |
| K-Nearest Neighbors | 0.9 | 0.83 | 0.92 | 0.87 | 0.89 |
| Random Forest | 0.85 | 0.86 | 0.84 | 0.86 | 0.85 |
| Gradient Boosting | 0.92 | 0.88 | 0.93 | 0.9 | 0.91 |

The best model is GB Model. We found 68 rules that explain the model.

The complete results of the project are written in the <a href="results.xlsx">results.xlsx</a> file.

## Conclusion
The project aims to predict vegetation fires in Kalimantan using machine learning models. The best model is selected based on the objective function, which is a GB model. The model is explained using rule-based explanation and fidelity. The results show that the model can predict vegetation fires with high accuracy.
