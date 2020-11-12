# Anomaly_Detection_of_NYC_Traffic
This project uses Neural Networks to detect anomalies in traffic time-series data.

## Project Overview

Knowing the state of a city's transportation network is vital to understanding future and current needs. The goal of this project is to leverage speed sensors installed around NYC and Data Science principles to detect and track traffic anomalies such as accidents. In total there were 135 useable sensors around NYC. The data contained 5 minute sampling rates for each sensor.

![all_sensors](https://user-images.githubusercontent.com/65979022/98952514-8bf44500-24c9-11eb-9ed1-7e466c38da4f.png)
Locations of all the various sensors.

In this repo you will find three notebooks detailing different stages of this project. The first one is the EDA notebook. This notebook walksthrough the cleaning and EDA of the dataset linked at the bottom. The next notebook is the modeling notebook. This notebook contains the steps I took to be able to predict traffic speeds at each of the sensors around NYC. The third and final notebook details how you utilize the prediction models for anomaly detection. This is the final modeling notebook.

## EDA

After exploring the data from NYC Open Data, it was apparent that each sensor location has a distinct traffic trend. Consequently, each sensor was trained with its own model.

![diff_loc_sensor](https://user-images.githubusercontent.com/65979022/98952527-8f87cc00-24c9-11eb-8d7b-dccdfb947947.png)
This image shows the difference in trends of sensors in the different locations.

![east_vs_west_sensor](https://user-images.githubusercontent.com/65979022/98952536-944c8000-24c9-11eb-97fc-d3df050ba888.png)
This image shows the difference in trends of sensors in the same location, but one is eastbound and the other is westbound.

## Modeling

Neural nets outperformed RNNs significantly. The best model had an RMSE of 0.37. Each model was trained on 30 minutes of data and predicted 15 minutes into the future.

![loss_distribution](https://user-images.githubusercontent.com/65979022/98952531-91ea2600-24c9-11eb-903b-29118d023603.png)
The average final model training and testing metrics. 

## Anomaly Detection

Anomaly detection was accomplished through measuring the prediction error. If the error was larger than 80% of the training standard deviation multiplied by the testing RMSE then it was considered an anomaly. The final product is a function that plots a real-time graph with markers indicating whether traffic speeds are anomalies or normal.

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
