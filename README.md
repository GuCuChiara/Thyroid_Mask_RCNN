# Thyroid_Mask_RCNN
Mask R-CNN for Thyroid nodules detection and instance segmentation on Keras and TensorFlow
This is an implementation of Mask R-CNN on Python 3, Keras, and TensorFlow version 1.x. 
The model generates bounding boxes and segmentation masks for each instance of a nodule in each thyroid ultrasound image. 
It's based on Feature Pyramid Network (FPN) and a ResNet101 backbone.


Different classes of images can be classified.
It is pending to modify the algorithm to be able to infer the length of the images.
Based on all of the above, the idea is to be able to infer the TIRADS scale, used in the classification of nodules detected by thyroid ultrasound.![image](https://user-images.githubusercontent.com/105322443/175075210-c2a33fbe-324b-483d-85bc-b66430652160.png)

Getting Started:
