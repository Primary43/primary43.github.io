# Customer-Segmentation-Prediction @ KPMG Virtual Internship

To understand customer value among a group of new customers lacking transaction history, different supervised classification ML and DL models were developed and assessed.
Business Use Case:
- The predicted segmentation can lead to more personalized marketing strategies, and improved customer engagement.
- Targeted promotions and incentives that resonate with each group's behavior and preferences can be used for potentially increasing customer lifetime value and loyalty.

![KPMG](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/kpmgg.png)
![Intro](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/1intro.png)


## Final WebApp on Heroku 
### [Visit the final WebApp on Heroku](https://app-db1-5d66c8de929e.herokuapp.com/) | [![GitHub](https://img.shields.io/badge/GitHub-View_on_GitHub-blue?logo=GitHub)](https://github.com/Primary43/kpmg-s-virtual-internship-customer-prediction)

### 1. Data Quality Assessment and Preprocessing [![GitHub](https://img.shields.io/badge/GitHub-View_on_GitHub-blue?logo=GitHub)](https://github.com/Primary43/kpmg-s-virtual-internship-customer-prediction/blob/main/ModelDevelopment/Notebooks/KPMG_Task1_DataAssessment.ipynb)

### 2. Exploratory Data Analysis
![EDA](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/2eda.png)
![EDA](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/2-2eda.png)
![EDA](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/2-3eda.png)
![EDA](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/2-4eda.png)



### 3. Model Development

- 3.1 Initially, an engineered target was obtained—a segmentation derived from the cluster of RFM (Recency, Frequency, Monetary value) model analyzing the behavior of existing customers with transaction records.
  
  ![RFM Cluster](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/cluster.png)
  ![RFM Cluster](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/3cluster.png)
  The result reveals low correlations between RFM clusters and other features, suggesting non-linear relationships. Facing challenges in identifying the underlying characteristics of the target RFM cluster, we implemented supervised learning algorithms to discern patterns and classify the target clusters.

- 3.2 Among different supervised classification ML and DL models, Two-Step Deep learning Classification Approach has proven to be more effective than the multi-classification approach, which has encountered challenges in accurately predicting each class in this given problem, compared to the model baseline (multi-classification deep learning model), Decision Tree, KNeighborsClassifier, EnsembleVoting model.
  ![model](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/4-1model.png)
  ![model](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/4-2model.png)
  ![model](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/4-3model.png)

- 3.3 Explainable AI (XAI) was applied to provide a clear view of each feature's influence on a prediction, indicating whether it raises or lowers the likelihood of a particular outcome. This includes the utilization of ExplainableDashboard and Dalex libraries.

  [![XAI Explainer](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/explainer.png)](https://app-db1-5d66c8de929e.herokuapp.com/db1/)
  
  ![XAI Arena](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/arena.png)
  
- 3.4 Model Prediction
  ![model](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship-customer-prediction/main/asset/5model.png)
### 4. Dashboard and Report

Presented on PowerBI, providing interactive visualizations and business intelligence capabilities.

![PowerBI Dashboard](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/demo1.png)

[![PowerBI](https://img.shields.io/badge/PowerBI-View_on_PowerBI-yellow?logo=PowerBI)](https://app-db1-5d66c8de929e.herokuapp.com/dashboard)  or [Access Full Version with PowerBI Account](https://app.powerbi.com/reportEmbed?reportId=3fb4b625-ae44-48b1-8ee4-5027bdbd8522&autoAuth=true&ctid=fdc0b06e-bbdf-4925-bd0a-86d8493b8af1)



### 5. Web application and model prediction

Deployed using Dash/Flask on Heroku for the capability of real-time prediction for both new input and existing customers based on demographic data.
[Visit the model prediction on Heroku](https://app-predict-ed883b6bdb3f.herokuapp.com/)


![Prediction WebApp](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/prediction_gif.gif)
