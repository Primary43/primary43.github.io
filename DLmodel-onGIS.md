# Deep Learning Computer Vision Model with ArchGIS Application
#### Objective:
- Develop an in-house computer vision process to extract feature information from aerial imagery datasets (RGB, NIR, and Lidar) with an integration of the DeepLearning Model and a GIS mapping system to extract building footprints and canopy trees from the data.
- Improve an image extraction performance compared to a traditional GIS platform like ENVI, the supervised machine learning workflow involves defining ROIs, stacking spectral layers, and cleaning up the classification output to reduce noise. This process is time-consuming and less accurate.

#### Software Requirement:
- ArcGIS deep learning module (Arcgis.learn), Python API, NVIDIA (CUDA) GPU processor

#### A Deep Learning Modeling Process Using ArcGIS and Python APIs 
 1. Inference Pre-Trained Object Detection Model Vs Pixel-Segmentation Model
 2. Transfer Learning Object Detection Model
 3. Pixel-Segmentation Model with Automate Pipeline for Deployment
 4. Inference Pre-Trained Point Cloud DL Model
    
---

## 1. Inference Pre-Trained Object Detection Model Vs Pixel-Segmentation Model
  Initially, we utilized Esri's pre-trained deep learning models to make an inference from the raw dataset and measure the prediction performance. The model specification and requirements include:
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_pretrained.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_compare1.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_pretrained3.png)

  The pre-trained pixel-segmentation model, designed for high-resolution (0.1 cm) imagery and capable of multi-class land cover classification, is well-suited for diverse datasets and yields accurate object predictions across various scenarios. However, this model's classification output is limited to pixel-level segmentation without distinguishing individual objects with unique identifiers for GIS mapping. To bridge this gap, enhancing the object detection model with labels derived from segmentation predictions is necessary for object-specific identification in GIS applications.

---

## 2. Transfer Learning Object Detection Model
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_transfer.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_transfer1.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_transfer4.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_transfer3.png)
- Limitation: 
  The deep learning model exhibits superior predictive capabilities for large-scale RGB image analysis when compared to traditional machine learning methods, eliminating the need for intricate image processing using different band combinations. Training the model with a greater volume of labeled data has enhanced its ability to discern more features within our specific dataset.

  Nevertheless, the model requires additional labels and samples to refine its average precision further. Given our limited GPU capacity, processing with a batch size of one will extend beyond 26 hours. To achieve heightened precision in object detection, a considerable extension of experimental time is necessary. As an alternative, leveraging pre-trained image segmentation models, coupled with post-processing, can streamline accurate rooftop extraction for expansive urban landscapes. Enhancing the automation of this workflow is feasible with tools like ModelBuilder.

---

## 3. Pixel-Segmentation Model with Automate Pipeline for Deployment
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_pretrained-post.png)
For the deployment phase, an automated pipeline processes each image raster set:
#### 3.1 Preprocessing: Images are resampled to meet the specifications of the model.
#### 3.2 Pixel Classification: A trained pixel-segmentation model classifies each pixel.
#### 3.3 Post-Processing: The model's output pixels are refined by:
- Removing noise and defining boundaries.
- Converting the cleaned pixels into polygons based on layer specifications.
- Standardizing the shape of building footprints.
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/pipeline.png)
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_pretrained-post2.png)


---

## 4. Inference Pre-Trained Point Cloud DL Model
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/model_lidar.png)

The Lidar dataset consists of Level 2 classified images from ICSM, pre-categorized into classes such as terrain, near terrain, trees, buildings, and power lines. For further refinement, a pre-trained deep learning model for point clouds is employed to cleanse noisy data and transform the raw point cloud into 2D and 3D polygons.
![ML](https://raw.githubusercontent.com/Primary43/DLmodel-onGIS/main/images/result.png)
