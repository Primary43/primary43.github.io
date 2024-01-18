# DL Computer Vision Model with ArchGIS Application
Objective:
- Develop an in-house computer vision process to extract feature information from aerial imagery datasets (RGB, NIR, and Lidar) with an integration of the DeepLearning Model and a GIS mapping system to extract building footprints and canopy trees from the data.
- Improve an image extraction performance compared to a traditional GIS platform like ENVI, the supervised machine learning workflow involves defining ROIs, stacking spectral layers, and cleaning up the classification output to reduce noise. This process is time-consuming and less accurate.

  
Software Requirement:
- ArcGIS deep learning module (Arcgis.learn)
- Python API
- NVIDIA (CUDA) GPU processor

 A Deep Learning Modeling Process Using ArcGIS and Python APIs 
 1. Inference Pre-Trained Model
 2. Transfer Learning
 3. Model Evaluation
 4. Final Pipeline and Model Deployment
---

## 1. Inference Pre-Trained Model
  Initially, we utilized Esri's pre-trained deep learning models to make an inference from the raw dataset and measure the prediction performance. The model specification and requirements include:
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_compare1.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_pretrained3.png)


*image_caption*



#
