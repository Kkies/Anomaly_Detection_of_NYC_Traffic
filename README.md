# Anomaly_Detection_of_NYC_Traffic
This project uses Neural Networks to detect anomalies in traffic time-series data.

## Project Overview

Knowing the state of a city's transportation network is vital to understanding future and current needs. This project aims to leverage speed sensors installed around NYC and Data Science principles to detect and track traffic anomalies such as accidents. In total, there were 135 useable sensors around NYC. The data contained 5-minute sampling rates for each sensor.

![all_sensors](https://user-images.githubusercontent.com/65979022/98952514-8bf44500-24c9-11eb-9ed1-7e466c38da4f.png)
Locations of all the various sensors.


In this repo, you will find three notebooks detailing different stages of this project. The first one is the "EDA" notebook. This notebook walks through the cleaning and EDA of the dataset linked at the bottom. The next notebook is the "modeling" notebook. This notebook contains the steps I took to predict traffic speeds at each of the sensors around NYC. The third and final notebook details how you utilize the prediction models for anomaly detection. This is the "final models" notebook.

## EDA

After exploring the data from NYC Open Data, it was apparent that each sensor location has a distinct traffic trend. Consequently, each sensor was trained with its own model.

![diff_loc_sensor](https://user-images.githubusercontent.com/65979022/98952527-8f87cc00-24c9-11eb-8d7b-dccdfb947947.png)
This image shows the different locations of the following two sensors.
![Sensor_142_weekdays](https://user-images.githubusercontent.com/65979022/98954296-a5968c00-24cb-11eb-85c0-a3249d99dbed.png)
![Sensor_222_weekdays](https://user-images.githubusercontent.com/65979022/98955434-dcb96d00-24cc-11eb-8cba-8b4d3d8e59f7.png)
The two graphs above show the different trends of sensors in different locations. For example in sensor 142, there is a more predominate cycle of traffic. You can clearly see the morning and afternoon rushhour. However, for sensor 222 there is a less defined cycle. Rather there always seems to be traffic.



![east_vs_west_sensor](https://user-images.githubusercontent.com/65979022/98952536-944c8000-24c9-11eb-97fc-d3df050ba888.png)
This image shows the location of the two sensors in the same place but recording speeds in different directions.
![Sensor_142_weekdays](https://user-images.githubusercontent.com/65979022/98954296-a5968c00-24cb-11eb-85c0-a3249d99dbed.png)
![Sensor_178_weekdays](https://user-images.githubusercontent.com/65979022/98955449-e216b780-24cc-11eb-8f9d-f0085b7dbbe9.png)
The two graphs above show the different trends of sensors in the same location, one is eastbound, and the other is westbound. 142 is the westbound sensor and you can see the brunt of rushhour is in the morning because of the number of people traveling into the city for work. Conversely, 178 is eastbound and you can clearly see that on fridays the afternoon rushhour is the worst. This is due to people leaving for the weekend. 


## Modeling

Neural nets outperformed RNNs significantly. The best model had an RMSE of 0.37. Each model was trained on 30 minutes of data and predicted 15 minutes into the future.

![loss_distribution](https://user-images.githubusercontent.com/65979022/98952531-91ea2600-24c9-11eb-903b-29118d023603.png)

The average final model training and testing RSME. You can see that both distributions are very similar. This is a good thing, becuase it shows that the models used were well-balanced.

## Anomaly Detection

Anomaly detection was accomplished by measuring the prediction error. If the error was larger than 80% of the training standard deviation multiplied by the testing RMSE, it was considered an anomaly. The final product is a function that plots a real-time graph with markers indicating whether traffic speeds are anomalies or normal.

## Conclusion

This project is an excellent start to understanding the complexities of city transportation. It can be utilized by city transportation officials to learn what areas are accident prone and need to have thier lanes expanded. However, the future of this project is where more global insight will occur. By creating a dashboard that visualizes all locations simultaneously, users will see city-wide traffic trends. This will allow users to see if anomalies in different locations trend together.

## Next Steps

Build a dashboard that shows what sensors are experiencing traffic anomalies.
Get access to real-time data.
Refine models for higher sampling rates.


## Sources

NYC Open Data https://data.cityofnewyork.us/Transportation/DOT-Traffic-Speeds-NBE/i4gi-tjb9

## Presentation
https://docs.google.com/presentation/d/1iTXJS8TDgT_aPQahIsIAHrmtvj17reK2Ir_a8mkS5RQ/edit?usp=sharing
