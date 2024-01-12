# Customer-Segmentation-Prediction @ KPMG Virtual Internship

To understand customer value among a group of new customers lacking transaction history, different supervised classification ML and DL models were developed and assessed.

![KPMG](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/kpmg.png)

## Final WebApp on Heroku
[Visit the final WebApp on Heroku](https://app-db1-5d66c8de929e.herokuapp.com/)

[![GitHub](https://img.shields.io/badge/GitHub-View_on_GitHub-blue?logo=GitHub)](https://github.com/Primary43/kpmg-s-virtual-internship-customer-prediction)


### 1. Model Development
[View the Model Development Slide](https://github.com/Primary43/kpmg-s-virtual-internship/blob/main/ModelDevelopment/Module_2_kpmg_slide.pdf)

- 1.1 Initially, an engineered target was obtained—a segmentation derived from the cluster of RFM (Recency, Frequency, Monetary value) model analyzing the behavior of existing customers with transaction records.
  
  ![RFM Cluster](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/cluster.png)

- 1.2 Among different supervised classification ML and DL models, Two-Step Deep learning Classification Approach has proven to be more effective than the multi-classification approach, which has encountered challenges in accurately predicting each class in this given problem, compared to the model baseline (multi-classification deep learning model), Decision Tree, KNeighborsClassifier, EnsembleVoting model.

  ![Two-Step Classification](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/two-step.png)

- 1.3 Explainable AI (XAI) was applied to provide a clear view of each feature's influence on a prediction, indicating whether it raises or lowers the likelihood of a particular outcome. This includes the utilization of ExplainableDashboard and Dalex libraries.

  ![XAI Explainer](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/explainer.png)
  
  ![XAI Arena](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/arena.png)

### 2. Dashboard and Report

Presented on PowerBI, providing interactive visualizations and business intelligence capabilities.

![PowerBI Dashboard](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/demo1.png)

### 3. Web application and model prediction

Deployed using Dash/Flask on Heroku for the capability of real-time prediction for both new input and existing customers based on demographic data.
[Visit the model prediction on Heroku](https://app-db1-5d66c8de929e.herokuapp.com/)

![Prediction WebApp](https://raw.githubusercontent.com/Primary43/kpmg-s-virtual-internship/main/asset/prediction.png)
