# Udacity Self Driving Car Nanodegree: Traffic Sign Classification

## Objective
Identifying traffic signs on road so that Self Driving Cars can be prevent from any accident.

## Introduction

### Self Driving Cars
Self Driving Cars are unmanned ground vehicles, also known as Autonomus Cars, Driverless Cars, Robotic Cars. 
<p align="center">
<img src="https://github.com/sansinghsanjay/udacity_self_driving_car_traffic_sign_classification/blob/master/images/self-driving-car.jpg">
</p>

### Technologies Used
Following are the technologies used by these Self Driving Cars to navigate:
1. Computer Vision and Machine Learning (AI) to find path, to classify traffic signs, etc.
2. Sensor Fusion to sense the surrounding moving vehicles.
3. Machine Learning (AI) for decision making.

### Why "Traffic Sign Classification"?
Traffic Signs are available on road for the proper handling of traffic. These signs helps in managing traffic and also prevents from accidents.

These signs also indicates about the condition of road, blind turns, appropriate speed limits as per the crowd present there.

Similar to human drivers, these traffic signs also helps to Self Driving Cars in making decisions.

## Programming Language
In this project, Python-2.7.12 is used with following packages:
1. numpy - 1.13.0
2. moviepy - 0.2.3.2
3. cv2 - 3.0.0 (Computer Vision)
4. TensorFlow - 1.2.1

## Data Set
Data set is provided by Udacity. This data set consists of 43 classes. Each class consists of tiny size images (not fixed size).

Following are the classes of given data:

0. Speed limit (20km/h): 211
1. Speed limit (30km/h): 2221
2. Speed limit (50km/h): 2251
3. Speed limit (60km/h): 1411
4. Speed limit (70km/h): 1981
5. Speed limit (80km/h): 1861
6. End of speed limit (80km/h)	421
7. Speed limit (100km/h)	1441
8. Speed limit (120km/h)	1411
9. No passing	1471
10. No passing for vehicles over 3.5 metric tons	2011
11. Right-of-way at the next intersection	1321
12. Priority road	2101
13. Yield	2161
14. Stop	781
15. No vehicles	631
16. Vehicles over 3.5 metric tons prohibited	421
17. No entry	1111
18. General caution	1201
19. Dangerous curve to the left	211
20. Dangerous curve to the right	361
21. Double curve	331
22. Bumpy road	391
23. Slippery road	511
24. Road narrows on the right	271
25. Road work	1501
26. Traffic signals	601
27. Pedestrians	241
28. Children crossing	541
29. Bicycles crossing	271
30. Beware of ice/snow	451
31. Wild animals crossing	781
32. End of all speed and passing limits	241
33. Turn right ahead	690
34. Turn left ahead	421
35. Ahead only	1201
36. Go straight or right	391
37. Go straight or left	211
38. Keep right	2071
39. Keep left	301
40. Roundabout mandatory	361
41. End of no passing	241
42. End of no passing by vehicles over 3.5 metric tons	241

From above it is clear that data is highly imbalanced. To make it balance, some image augmentation operations are applied on classes having less number of images.

## Algorithm
A Convolutional Neural Network is used here. This CNN is written in Python - TensorFlow. Following is the architecture of this CNN:
1. Three convolutional layer
2. One fully connected layer
3. Three max-pooling layer
4. One dropout layer
5. Activation Function Used: "relu"
6. Optimizer: "AdamOptimizer"
7. Learning Rate: 0.0002

Data is augmented by using different image augmentation operations like:
1. Rotation by 45 degrees
2. Image noising
3. Gaussian blurring

Above image augmentation operations are applied only on those classes which have less number of images.

Given data is splitted into two sets by checking stratify option in train_test_split:
1. Train data: Stratified 90% of given data
2. Validation data: Stratified 10% of given data

CNN is trained for 300 epochs. Following are the relevant plots showing training loss/accuracy and validation loss/accuracy at each epoch:
[plots] [plots]

Achieved accuracy on validation data set after 300 epochs is 95.51%.

## How To Use?
To use this project:
1. Clone this github repository.
2. Open and use ipython notebook under "scripts" sub-directory.

## Limitations
1. On turns, this code is giving weired output.
2. If the position of lane get changed (like width of lanes), then this code may not be able to detect the lanes even if lanes are straight. This is because region of interest is hard coded here, its not generic.
3. As per some latest researches, it came out that if someone sticks any simple sticker on traffic sign then these neural network model easily gets failed and can identify "stop" as "speed limit 80 kmph".
