# Anomaly_Detection_of_NYC_Traffic
This project uses Neural Networks to detect anomalies in traffic time-series data.

## Project Overview

Knowing the state of a city's transportation network is vital to understanding future and current needs. The goal of this project is to leverage speed sensors installed around NYC and Data Science principles to detect and track traffic anomalies such as accidents. In total there were 135 useable sensors around NYC. The data contained 5 minute sampling rates for each sensor.

Sensor locations image

In this repo you will find three notebooks detailing different stages of this project. The first one is the EDA notebook. This notebook walksthrough the cleaning and EDA of the dataset linked at the bottom. The next notebook is the modeling notebook. This notebook contains the steps I took to be able to predict traffic speeds at each of the sensors around NYC. The third and final notebook details how you utilize the prediction models for anomaly detection. This is the final modeling notebook.

## EDA

After exploring the data from NYC Open Data, it was apparent that each sensor location has a distinct traffic trend. Consequently, each sensor was trained with its own model.

ImageImage


## Modeling

Neural nets outperformed RNNs significantly. The best model had an RMSE of 0.37. Each model was trained on 30 minutes of data and predicted 15 minutes into the future.

## Anomaly Detection

Anomaly detection was accomplished through measuring the prediction error. If the error was larger than 80% of the training standard deviation multiplied by the testing RMSE then it was considered an anomaly. The final product is a function that plots a real-time graph with markers indicating whether traffic speeds are anomalies or normal.

Image Image

## Conclusion

This project is a good start to understanding the complexities of city transportation. However, the future of this project is where deeper insight will occur. By creating a dashboard that visualizes all locations simultaneously, users will be able to see city-wide traffic trends. 

## Next Steps

Build a dashboard that shows what sensors are experiencing traffic anomalies
Get access to real-time data
Refine models for higher sampling rates


## Sources

NYC Open Data https://data.cityofnewyork.us/Transportation/DOT-Traffic-Speeds-NBE/i4gi-tjb9

## Presentation
https://docs.google.com/presentation/d/1iTXJS8TDgT_aPQahIsIAHrmtvj17reK2Ir_a8mkS5RQ/edit?usp=sharing
