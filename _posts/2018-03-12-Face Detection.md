---
layout:     post
title:      Face Detection
subtitle:   unfriendly API!(6000C CV project No.2)
date:       2018-03-12
author:     CHEN	Yuxiang
header-img: img/faceDetection/good3.jpg
catalog: true
tags:
    - Matlab
    - HOG
    - linear SVM
---
# A.Project Description
### Project Details

The project detail is in [6000C Homepage](https://home.cse.ust.hk/~cktang/msbd6000c/Password_Only/projects/iscissor/index.html). 

Due to the intranet's limitation, you can click the [Brown CS143](http://cs.brown.edu/courses/cs143/2011/results/proj4/psastras/) for temporary reference.



### Develop environment
Develop Environment: MATLAB + vl_feat

Programming language: MATLAB

System: MacOS 10.13

# B.Final result
### 1. training performance
![](https://ws2.sinaimg.cn/large/006tNc79gy1fp9z83b2e0j30kw0a475u.jpg)


# C.Steps
### 1. Load positive training crops and random negative examples

details of load positive training crops：

- extract file names of images
- load the images
- Rgb2gray operation and Normalization
- compute HOG descriptors
- save the HOG features

Details of load random negative examples:

- compute the candidates of possible values of x_min,y_min of cropped images.
- parallel implement the generating candidates of negative samples.
- extract their HOG features and save it.

### 2. Train Classifier

Details of training:

- concatenate the features of positive and random negative samples along the x-axis. And transpose the whole X matrix(feature matrix).
- concatenate the labels of positive and negative samples.
- set the lambda(The regularization parameter).
- train the w and b by vl_svmtrain.

### 3. Examine learned classifier

visualize the perfect HOG descriptors trained for human detection.
![](https://ws2.sinaimg.cn/large/006tNc79gy1fp9zbukoy3j30v40ncwh0.jpg)

Visualize how well separated the positive and negative examples are at
training time.
![](https://ws2.sinaimg.cn/large/006tNc79gy1fp9zr0ok90j30v40nc3z7.jpg)

### 4. Run detector on test set.
Details

- set the pre-filtering threshold.
- for a single image, scale the original image by various times.
- compute all candidates of possible x_min,y_min,x_max,y_max.
- compute the corresponding boxes in original image.
- send all candidates filtered by threshold into non-max suppression function.
- save the possible result for face detection.

### 5. Evaluate and Visualize detections

Match the figure 6
![](https://ws4.sinaimg.cn/large/006tNc79gy1fpa008aplkj30v40ncjsj.jpg)
Average precision
![](https://ws3.sinaimg.cn/large/006tNc79gy1fpa01k41k0j30v40ncjsg.jpg)

Sample result
![](https://ws4.sinaimg.cn/large/006tNc79gy1fpa02d995mj30mq0fydgw.jpg)
![](https://ws1.sinaimg.cn/large/006tNc79gy1fpa03994amj30mq0fy0u0.jpg)
   

# D. Bonus
### 1. Hard negative mining
Details

- run detector on non-face images randomly 
- choose the images that the most unlikely to be human face 
- after pre-filtering, send them into non-max suppression.
- save the hard negative features.
- train the SVM again using the positive samples and hard negative samples.
- run detector on test set again.

### 2.adjusting hyper-parameters
1. The threshold for firstly filtering the detection.
2. The threshold for negative mining.
3. The threshold for secondly filtering the detection by detectors trained by hard negative samples.
4. The regularization parameter of linear SVM.


>最后附上GitHub：<https://github.com/wsgtcyx/IntelligentScissors>



