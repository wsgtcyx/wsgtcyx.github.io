---
layout:     post
title:      Intelligent Scissors
subtitle:   So complicated!(6000C CV project No.1)
date:       2018-02-07
author:     CHEN	Yuxiang
header-img: img/post-bg-os-metro.jpg
catalog: true
tags:
    - C++
    - QT
    - Priority Queue
    - Opencv
    
---
# A.Project Description
### Project Details

The project detail is in [6000C Homepage](https://home.cse.ust.hk/~cktang/msbd6000c/Password_Only/projects/iscissor/index.html). 

Due to the intranet's limitation, you can click the [Washington CSE 455](https://courses.cs.washington.edu/courses/cse455/03wi/projects/project1/web/project1.htm) for temporary referrence, which is quite similar.

### Fantastic show(automatically extract the hat out)
![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/dynamic.gif)

### Develop environment
Develop Environment: Qt5 + Opencv3

Programming language: C++

System: MacOS 10.13

# B.General usage
#### 1. Load Picture
You can choose any picture in your computer by selecting in the File Manager.

For example, I **open** an example picture of Opencv.
![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/open file.png)


#### 2. Choose Mode
For universal Use, we choose **Min Path**.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/choose mode.png)

#### 3. Start drawing
Now I click **start** to start drawing.

You can see the two yellow points in the picture are the positions I have clicked. After the first seed is confirmed, we would dynamically demonstrate a min path (Red curve) from the seed point to the current mouse position. 

It is obviously that the algorithm would allow the min path go along with the edge of some essential factors in the picture(such as the hat of lena).

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/second draw.png)

#### 4. Undo
We offer the **undo** function in the drawing. You can click undo to delete the last contour in the Picture. Of course you can click "undo" many times to delete many contour.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/undo .png)

#### 5. Finish drawing and Save mask

Now, we **finish drawing** and save mask to the computer.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/save_mask.png)

**Mask:**

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/mask.png)

# C.Other Modes

#### 1. Image Only
show original image without contour superimposed on it.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/mode1.png)

#### 2.Image with Contour
show original image with contours superimposed on it.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/mode2.png)

#### 3. Pixel Node
Draw a cost graph with original image pixel colors at the center of each 3by3 window, and black everywhere else.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/mode3.png)

#### 4. Cost Graph
Draw a cost graph with both pixel colors and link costs, where you can see whether your cost computation is reasonable or not, e.g., low cost (dark intensity) for links along image edges.

![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/mode4.png)

#### 5. Path Tree
show minimum path tree in the cost graph for the current seed; You can use the counter widget to simulate how the tree is computed by specifying the number of expanded nodes. The tree consists of links with yellow color. The back track direction (towards the seed) goes from light yellow to dark yellow.
 
![](https://raw.githubusercontent.com/wsgtcyx/wsgtcyx.github.io/master/img/intelligent scissors/path tree.gif)

# D.small fancy functions
- zoom in(out)
- save contour(mask)


>最后附上GitHub：<https://github.com/wsgtcyx/IntelligentScissors>


<!-- <video controls="" preload="none" poster="http://media.w3.org/2010/05/sintel/poster.png"><source src="http://media.w3.org/2010/05/sintel/trailer.mp4" type="video/mp4"><source src="http://media.w3.org/2010/05/sintel/trailer.webm" type="video/webm"><source src="http://media.w3.org/2010/05/sintel/trailer.ogv" type="video/ogg"><p>Your user agent does not support the HTML5 Video element.</p></video>-->
