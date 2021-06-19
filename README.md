# Data-Scince-Project
In this Peoject we have to classify and localize the text fields in an ID card. It is an object detection problem And to solve this problem we have to use transfer learning in which we will use the resnet50 model with pre trained coco weights to detect the text fields in an ID cards.We have considered five classes for this project which are:
*	First Name
*	Last Name
*	Country
*	CNIC No
*	Date of Birth

Also, another class to mention is the background so including background we have **6 classes**.
## Requirements
* Tensorflow Version: 1.15
* Keras Version: 2.0.8

Other Python Libraries:
![image](https://user-images.githubusercontent.com/37701187/121135494-00b81380-c84e-11eb-8ced-fc6292402bcb.png)


## Working
### Dataset Generation
#### Image Collection from Google
To make our dataset we have had gathered images of ID cards and passports pics from famous search engines so we had collected 61 total images and our consisted of 4 sets. The categories of dataset along with their quantity is mentioned below:
1.	Pakistani ID card pics = 17
2.	Pakistani Passport pics = 18
3.	UK ID card pics = 11
4.	UK Passports pics = 15

#### Image Augmentation to Enlarge Dataset
We have used built-in image augmentation tool which takes original dataset along with its annotated files. It applies different operations such as mirroring, rotation and changing band values to augment the data to make the dataset larger. So after doing that the augmented dataset had 1220 images. The categories of dataset along with their quantity is mentioned below:
1.	Pakistani ID card pics   = 17 * 20 = 340
2.	Pakistani Passport pics = 18 * 20  = 360
3.	UK ID card pics           = 11 * 20  = 220
4.	UK Passport Pics         = 15 * 20  = 300

#### Augmentation Techniques
1. Manual Rotation
2. 	Rotate Image by +45 or -45 degrees.
3.	Scale Image to 80-120% of their size
4.	Shear Image to -16 to 16 degrees.
5. Blur image by applying one of the following
   * Gaussian Blur
   * Average Blur
   * Median Blur
6.	Sharpen an Image
7.	Emboss Image
8.	Add Gaussian Noise to Image
9.	Randomly Remove 10% of the pixels
10.	Invert Image
11.	Change Brightness
12.	Add to Hue and Saturation
13.	Improve or Worsen the Contrast
14.	Convert Image to its super pixel form.

### Train-Test Split
The dataset had 1220 images so we made our train test split as 950:270.

### Layer Removal
In the M-RCNN model we removed these layers:
1.	Mrcnn_class_logits
2.	Mrcnnbboxfc
3.	Mrcnnbbox
4.	Mrcnn_mask

### Training Configuration
![image](https://user-images.githubusercontent.com/37701187/121134463-dade3f00-c84c-11eb-9914-b6a948068b94.png)

## Output Images
### Original Image with bounding boxed
![image](https://user-images.githubusercontent.com/37701187/121134863-54762d00-c84d-11eb-9f11-d6d2957f7c42.png)
### Bounding Boxes Made by Model on same Image
![image](https://user-images.githubusercontent.com/37701187/121135021-81c2db00-c84d-11eb-98fa-55968f025cad.png)





