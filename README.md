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

## Contact

Subhanshu Arya - subhanshu20101@iiitnr.edu.in

Harsh Pandey - harsh20101@iiitnr.edu.in
