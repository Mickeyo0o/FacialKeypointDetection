# Facial Keypoint Detection (Pose Estimation) - Computer Vision

Welcome to our Facial Keypoint Detection project! In this repository, we explore different models to perform facial keypoints detection with the ultimate goal of creating a filter that adds sunglasses to a taken picture.

## Repository Structure:

* <b>Report.ipynb:</b> This Jupyter notebook contains the main model creation, training, testing, and analysis.
* <b>model*.json:</b> These files contain the structure of each model.
* <b>model_history*.pickle:</b> These files contain the training history of each model.
* <b>filters folder:</b> Contains the image of the sunglasses filter along with keypoint references.
* <b>app folder:</b> Contains the HTML application of the sunglasses filter.
* <b>keras_to_onnx.py:</b> This file allows translating models from Keras to ONNX for use in our application.

## Features:

* <b>Data:</b> The dataset contains 7049 images of different faces along with their keypoints, available [here](https://www.kaggle.com/competitions/facial-keypoints-detection/data?select=training.zip).
* <b>Data loading and preprocessing:</b> We removed data points with missing values and resized the images.
* <b>Data generation:</b> We created generators that can continuously generate new images based on the dataset images. Three instances of generators were used, each based on a different part of the dataset to avoid test set leakage.
* <b>Model creation:</b> We developed four models:
    * First model: Fully trained and created by ourselves.
    * Second model: Uses MobileNetV2 along with our own layers and trained by ourselves.
    * Third model: Again created fully by ourselves, it improves speed compared to the first model but results in loss of accuracy.
    * Fourth model: Uses MobileNetV2 with pretrained weights and our additional layers.
* <b>Methodology analysis:</b> The notebook contains information about hyperparameters, metrics, and other details.
* <b>Results analysis:</b> Comparison of all models and conclusions drawn from the analyses.
* <b>Filter application:</b> Visualization of the application of sunglasses filter.

## Application:

Additionally, we have created an application that can be run in HTML using FastAPI.

## Usage:

* The notebook named Report.ipynb contains the entire process of model development, training, and visualization of sunglasses filter results. It can be downloaded or viewed on GitHub. Our model weights files are stored on Google Drive as they were too large to be included directly. These files are available [here](https://drive.google.com/drive/u/2/folders/16EUYvUpze603XQKlXv5_1Mufg4-lRYPU). If you wish to train these models again, you can omit this download. Additionally, the training data should be placed in the training folder.

* The HTML app can be deployed on localhost, but it requires the compression of the model to ONNX. A landmark of the first model considered in the notebook is available on our Google Drive here. The landmark file needs to be placed into the "\app\api\model\weights" folder. Additional required libraries:
    * opencv-contrib-python
    * onnxruntime==1.16.1
    * fastapi==0.103.2
    * uvicorn==0.23.2
    * numpy==1.26.3
    * pydantic==2.4.2

## Creators:

* Kajetan Sulwiński (ekohachi22)
* Mikołaj Marmurowicz (Mickeyo0o)