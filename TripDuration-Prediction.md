# TripDuration-Prediction-based-on-Locational-cluster

This objective is to apply statistical analysis and predictive modeling techniques by integrating location cluster features into a linear regression model aimed at predicting taxi trip durations.


[![GitHub](https://img.shields.io/badge/GitHub-View_on_GitHub-blue?logo=GitHub)](https://github.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster)

### Task 1: Exploratory Data Analysis (EDA) and Variance Analysis
- 1.1 Evaluation of temporal patterns with distance and duration.
- 1.2 Exploration of data specific to vendors and flags.
- 1.3 Investigation of correlations among passengers.
- 1.4 Analysis of spatial data.

A synthesis of the findings was performed, focusing on patterns of pickups and drop-offs over different time frames.

![Temporal Patterns](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/temporal.png)

![Spatial Data Gif](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/gif.gif)

### Task 2: Feature Engineering
- 2.1 Development of a model for clustering based on geographical location.
- 2.2 Incorporation of temporal features.

![Locational Cluster](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/locational%20cluster.png)

### Task 3: A Comparative Analysis Across Four Distinct Regression Models
- 3.1 A baseline model utilizing only the significant variables identified in the EDA.
- 3.2 A comprehensive model incorporating all features.
- 3.3 A model employing backward selection for feature optimization.
- 3.4 A geospatial clustering model utilizing K-means to categorize latitude and longitude data into 29 unique location clusters.

![Assumption of Linearity](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/assumption%20of%20linearity.png)

![Coefficient Plot](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/CoefPlot.png)

### Results
The regression model’s accuracy was assessed using Mean Absolute Error (MAE) and Mean Squared Error (MSE) to gauge the average prediction error, while the R-squared (R²) and Adjusted R-squared values were used to quantify the model's fit to the data. The integration of location cluster features into the baseline model resulted in a marked performance improvement, as demonstrated by reduced MAE and MSE values and an enhanced R² value of 0.8, signifying that 80% of the variability in the dependent variable can now be explained by the model's independent variables.

![Results](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/result.png)
