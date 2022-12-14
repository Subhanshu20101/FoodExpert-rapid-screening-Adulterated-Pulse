# FoodExpert-rapid-screening-Adulterated-Pulse
This is a portable intelligent device for rapid screening of pulse adulterated with metanil yellow.
## About the project

![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/arch.png)
Food adulteration is a major problem around the world since adulterants can cause cancer.
The majority of adulteration detection methods currently in use are laboratory-based, which takes time, money, and human evaluation.
To address this issue, we propose, FoodExpert, which detects the metanil yellow adulteration in pulse samples based on image processing and machine learning techniques. The system takes a picture of a pulse sample and recognises the region of interest and other crucial characteristics as features automatically. The model has been deployed successfully on an Raspberry-based hardware prototype, proving its eligibility for real-time applications.

## Features

* The proposed device collects image samples using a camera as a sensor, after which it performs preprocessing and feature engineering to extract relevant features, which are then used to classify the adulterant sample with a level of adulteration. 
* The model effectively distinguishes between different adulteration degrees using color space characteristics (bins of K-means Clustering) as an input vector. 
* The model's effectiveness on a test set of 2123 data points was about 94%, and on a real-world data set of 100 photos, it was about 87%. The pictures' Root Mean Square (RMS) error for the colour characteristics of random grains is 0.096. 

## Technology Stack
* [Visual Studio Code](https://code.visualstudio.com/)
* [Python 3.8.0](https://www.python.org/downloads/release/python-380/)
* [OpenCV](https://opencv.org/)
* [EvalML](https://evalml.alteryx.com/en/stable/#)
* [Raspberry Pi](https://www.raspberrypi.com/)

## Methodology
### Preprocessing and Contour Extraction
OpenCV was used for image preprocessing. The procedures are mentioned below-
* Grey Scaling
* Erosion
* Dilation
* Thresholding
* Modified Canny Edge Detecion

![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/Preprocessing.png)

### Feature extraction and K-means Clustering
After the contour detection, we plot the contour on a black masked image to remove any excess background bleed. We return to contour detection after successfully plotting, which again estimates a bounding ellipse around each pulse. To maximise ROI without including background, we fit a maximum area rectangle inside the detected ellipse. Also, because the fitted rectangle can be in various rotated configurations, we wrap a perspective transformation around it to make it a normal rectangle as shown below. 

![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/Max_are_elleipse.png)        ![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/wrapPerspective.png)

### Machine learning model Execution

We used the EvalML library to select the model with the best performance. As shown below, the Random Forest Classifier was the best fit model. 

![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/models.png)  

### Implementing Hardware Setup
We used Raspeberry Pi as our microcontroller and a CMOS based pixel sensor to capture images. The remaining setup is shown below.


![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/hardware.png)

## Some Results
* Classification metrics based on test dataset
 
![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/metrics.png)

* Confusion matrix for Overall Dataset

![alt text](https://github.com/Subhanshu20101/FoodExpert-rapid-screening-Adulterated-Pulse/blob/main/images/confusiionmatrix.png)


## Contact

Subhanshu Arya - subhanshu20101@iiitnr.edu.in

Harsh Pandey - harsh20101@iiitnr.edu.in
