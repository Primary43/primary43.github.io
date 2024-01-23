# TripDuration-Prediction-based-on-Locational-cluster + MLFlow

This objective is to apply statistical analysis and predictive modeling techniques by integrating location cluster features into a linear regression model aimed at predicting taxi trip durations.
As this dataset contains taxi trip duration records over six months, necessitating scalable data handling and integration with additional data like weather or events in the next development phase. In this context:
- PySpark offers scalable data processing and efficient integration, ideal for expanding datasets and building advanced data pipelines.
- MLflow manages the machine learning lifecycle, covering experimentation, reproducibility, and monitoring.
![brick](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/brick.png)


[![GitHub](https://img.shields.io/badge/GitHub-View_on_GitHub-blue?logo=GitHub)](https://github.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster)

### Task 1: Data Ingestion 
Data ingestion into Delta Lake from an AWS S3 bucket enhances reliability and performance, supporting complex ETL operations. The process involves cleansing and transforming the data, as well as feature extraction for analytical purposes. This includes extracting date components from datetime fields and deriving insights from geospatial data.


### Task 2: Exploratory Data Analysis (EDA) and Variance Analysis [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Primary43/TripDuration-Prediction-based-on-Locational-cluster/blob/main/02_EDA.ipynb)

- 2.1 Evaluation of temporal patterns with distance and duration.
- 2.2 Exploration of data specific to vendors and flags.
- 2.3 Investigation of correlations among passengers.
- 2.4 Analysis of spatial data.

A synthesis of the findings was performed, focusing on patterns of pickups and drop-offs over different time frames.

![Temporal Patterns](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/temporal.png)

![Spatial Data Gif](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/gif.gif)

### Task 3: Feature Transforming and Engineering Pipeline for Training and Testing Sets
- 3.1 Implemented a data transformation pipeline: encompassing data filtering, logarithmic transformations for normalization, feature scaling for uniformity, and encoding of categorical variables to prepare for machine learning analysis.
![before](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/before.png)
![after](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/after.png)


- 3.2 Integrated cluster-based geographical features into the training and testing sets. This entailed combining pickup and drop-off coordinates, applying scaling to normalize location data, and employing KMeans clustering. An automated hyperparameter tuning process determined the optimal number of clusters, resulting in 29 distinct geographical segments based on pickup and drop-off points.

![Locational Cluster](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/locational%20cluster.png)

### Task 4: Inspect assumption Assumption of Linear Regression
A comprehensive assessment of linear regression assumptions was conducted, involving an evaluation of the model's coefficients, variance inflation factors to detect multicollinearity and analysis of residual plots. The findings indicated several deviations from the ideal conditions.
- Residual Plot: The observed pattern indicates heteroscedasticity, with non-constant variance in the residuals across the fitted value range.
- Distribution of Error Terms: The residual histogram displayed a bell shape but was not symmetrical, peaking slightly left of the center.
- Q-Q Plot: The central quantiles align with the theoretical normal line, but the tails exhibit deviations, suggesting that the residuals have heavier tails than a normal distribution.

  Given these observations, where the prerequisites for optimal linear regression are not completely satisfied, the investigation will pivot toward robust regression techniques. These methods, which include LASSO, Ridge, and Elastic Net, are designed to enhance the model's robustness against outliers and other violations of regression assumptions.
![Assumption of Linearity](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/assumption%20of%20linearity.png)


### Task 5: Model Training and Evaluation Tracking with MLFlow [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Primary43/TripDuration-Prediction-based-on-Locational-cluster/blob/main/03_Model_MLFlow.ipynb)
Four distinct robust regression algorithms include LASSO, Ridge, Elastic Net, and XGBoost. The K-fold cross-validation was employed to identify the optimal parameters for each model on three unique feature sets. 
- A baseline model utilizing only the significant variables identified in the EDA.
- A comprehensive model incorporating all features.
- A geospatial clustering model utilizing K-means to categorize latitude and longitude data into 29 unique location clusters.

![Coefficient Plot](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/CoefPlot.png)

Lastly, an MLflow tracking server was utilized to systematically record models, parameters, metrics, and artifacts, ensuring comprehensive logging of the experimentation process.
### Results
The exploration of MLflow logs indicates that incorporating geospatial features and clustering-based location data into the XGBoost model leads to a marked improvement over traditional linear models like Lasso, Ridge, and ElasticNet. This improvement is quantitatively evident in the enhanced R2, which has seen an increase from 0.65 to 0.78, and a decrease in the Mean Squared Error (MSE) from 0.05 to 0.03. These figures underscore the significant impact of geospatial features and the derived clustering information on the model's predictive accuracy, highlighting the importance of spatial context in the predictive modeling of taxi durations.

![mlflow_table](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/mlflow_table.png)
![mlflow](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/mlflow.png)

| ![feature](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/mlflow_feature.png) | ![feature2](https://raw.githubusercontent.com/Primary43/TripDuration-Prediction-based-on-Locational-cluster/main/asset/mlflow_feature2.png) |



