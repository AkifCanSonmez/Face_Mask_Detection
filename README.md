# Face_Mask_Detection
![with mask](https://user-images.githubusercontent.com/78687240/158613032-159b26f5-ec42-4b98-a5bd-968fbbea547b.png)

![without mask](https://user-images.githubusercontent.com/78687240/158613053-9b999210-d7bf-4a10-9c52-cada4de99b48.png)

## THE AIM OF THE PROJECT

The aim of this project is to develop a system that detects whether there is a mask on the face of the person in the image coming from the camera using artificial intelligence techniques.

## SUMMARY of PROJECT

## Note: The dataset link is in the source code.

This project basically consists of two parts. In the first part, a dataset of approximately 3800 unmasked and 3700 masked face images from Kaggle was used to feed a deep learning model that would classify whether the person had a mask on their face. This model has been saved for use in the second part of the project. In the second part, a camera recording was started and the position of the face of the person in the image was instantly detected, and then, using this location information, it was ensured to determine whether there was a mask on the face of the person with the image taken.

## Source Code: https://github.com/AkifCanSonmez/Face_Mask_Detection

## TECHNOLOGIES USED IN THE PROJECT

### Used IDE: Jupyter Notebook

### Used Programming Language: Python

## Used Libraries:

Face_recognation: A python library developed to simplify facial recognition.

Keras:It is a deep learning library for Python that provides a convenient way to define and train almost any type of deep learning model. Keras is a high-level neural networks API written in Python that can run on Tensorflow, Theano, and CNTK.

OpenCV: OpenCV (Open Source Computer Vision) is an open source image processing library.

NumPy: A library for the Python programming language that supports large, multidimensional arrays and matrices, adding high-level mathematical functions to operate on those arrays.


# PROJECT STAGES

## PART 1: 

### STEP 1 
Dataset is defined as 80% train, 20% test, classes are determined. Preprocessing is performed.

![1](https://user-images.githubusercontent.com/78687240/158424292-2d1d6d98-e19f-41f9-aab1-cc5da59bac92.png)

### STEP 2
Using Image Data Generator (https://www.analyticsvidhya.com/blog/2020/08/image-augmentation-on-the-fly-using-keras-imagedatagenerator/#:~:text=ImageDataGenerator%20class%20allows%20you%20to,value%20in%20the%20rotation_range%20argument.)

### STEP 2 
The model we used was built with Keras using Convolutional Neural Networks (CNN). A convolutional neural network is a special type of deep neural network that performs extremely well for image classification purposes. A CNN basically consists of an input layer, an output layer, and a hidden layer, which can have multiple layers. A convolution operation is performed on these layers using a filter that performs 2D matrix multiplication on the layer and filter. The CNN model architecture consists of the following layers:

Convolutional layer; 32 nodes, kernel size 4

Convolutional layer; 32 nodes, kernel size 4

Convolutional layer; 32 nodes, kernel size 4

Fully connected layer; 128 nodes

The last layer is also a 1-node fully connected layer. A Relu activation function is used in all layers except the output layer where we use Sigmoid.

![3](https://user-images.githubusercontent.com/78687240/158425193-24ee28b6-5f45-4f24-a229-bba52c3cdab6.png)

## PART 2:

### STEP 1
In order to determine the position of the faces in the image, a pre-prepared XML file (Face Cascade) is defined by OpenCV and the model trained in Part 1 is loaded. 

![5](https://user-images.githubusercontent.com/78687240/158425550-3e7ceaaf-36d0-44cd-92f7-3edb03217cef.png)

### Step 2
The camera opens; The position of the person's face in the camera is determined by the cascade classifier, for a better estimation, the face of the person in the image is cropped into a picture with the location information. After the preprocessing process, the model is predicted.

![7](https://user-images.githubusercontent.com/78687240/158566726-509cb6a2-17eb-415a-975b-57d0eca8526f.png)
