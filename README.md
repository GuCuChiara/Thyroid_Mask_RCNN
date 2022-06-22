# Thyroid_Mask_RCNN
Mask R-CNN for Thyroid nodules detection and instance segmentation on Keras and TensorFlow
This is an implementation of Mask R-CNN on Python 3, Keras, and TensorFlow version 1.x. 
The model generates bounding boxes and segmentation masks for each instance of a nodule in each thyroid ultrasound image. 
It's based on Feature Pyramid Network (FPN) and a ResNet101 backbone.


Different classes of images can be classified.
It is pending to modify the algorithm to be able to infer the length of the images.
Based on all of the above, the idea is to be able to infer the TIRADS scale, used in the classification of nodules detected by thyroid ultrasound.
![Screenshot (1499)](https://user-images.githubusercontent.com/105322443/175176177-b2d44334-7cda-4aa5-a3e1-ad20d694b17d.png)

# Requirements
Python 3.7, TensorFlow 1.3, Keras 2.0.8 and other common packages listed in `requirements.txt`.

# Training on MS COCO
We're providing pre-trained weights for MS COCO to make it easier to start. 
You can use those weights as a starting point to train your own variation on the network.

# Installation
1. Clone this repository
2. Download pre-trained COCO weights (mask_rcnn_coco.h5) from the [releases page](https://github.com/matterport/Mask_RCNN/releases).
3.You can download COCO weights from my google drive: https://drive.google.com/file/d/1L6VYJx__E4_rmds-C4o2KJzumBmZ-TAE/view?usp=sharing
4. Add it into folder Mask_RCNN
5. Main file is Train_Mask_RCNN_.ipynb
6. The dataset:
```
The dataset with its images were uploaded to https://www.makesense.ai to draw the nodular image masks manually.
The generated annotations.json file contains all the masks of the dataset, used for training.
The dataset was compressed in the images.zip file, later the images are extracted in the "dataset" folder
As it is a test version, the dataset is small, and logically the prediction is going to be of low quality.
```
7. Basic training data (Mask_RCNN\mrcnn\m_rcnn.py):
```
-BACKBONE = "resnet101"
-LR=0.001
-EPOCHS = 10
-STEPS_PER_EPOCH = 250
-VALIDATION_STEPS = 6
-DETECTION_MIN_CONFIDENCE = 0.9
-Dataset split = 90% train / 10% validation
-NUM_CLASSES = 1 + 2 (background + (hypo node, iso node)) you can add more classes.
-CLASSES: "categories":[{"id":1,"name":"nodulo-iso"},{"id":2,"name":"nodulo-hipo"}]
Train and Validation are automatically created, 90% is used for training and 10% for validation.
```
![Screenshot (1498)](https://user-images.githubusercontent.com/105322443/175176741-ae55d091-5b46-49b6-a5e2-27b409038886.png)

