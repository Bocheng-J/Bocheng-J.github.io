---
layout:     post
title:      Kalman filter
subtitle:   Kalman filter
date:       2020-05-04
author:     oscar
header-img: img/post_bg_20200504.jpg
catalog: true
tags:
    - Kalman filter
    - study notes
---

>  [Kalman filter](https://en.wikipedia.org/wiki/Kalman_filter).


# Introduction videos
> video source: 
> 如何通俗并尽可能详细地解释卡尔曼滤波？ - 云羽落的回答 - 知乎 https://www.zhihu.com/question/23971601/answer/839664224

## 1. Why use Kalman Filters:

<iframe src="//player.bilibili.com/player.html?aid=370545584&bvid=BV1pZ4y1s7XB&cid=187145554&page=1" scrolling="no" width="600px" height="450px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

## 2. State Observers:

<iframe src="//player.bilibili.com/player.html?aid=968070266&bvid=BV11p4y197Ly&cid=187145687&page=1" scrolling="no" width="600px" height="450px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>


## 3. Optimal State Estimator:


## 4. Optimal State Estimator Algorithm:
<iframe src="//player.bilibili.com/player.html?aid=200533156&bvid=BV1ez411z7Qo&cid=187146006&page=1" scrolling="no" width="600px" height="450px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

## 5. Nonlinear State Estimators:
<iframe src="//player.bilibili.com/player.html?aid=710515346&bvid=BV1sQ4y1N7e6&cid=187146091&page=1" scrolling="no" width="600px" height="450px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

## 6. How to Use a Kalman Filter in Simulink:


## 7. How to Use an Extended Kalman FIlter in SImulink:
<iframe src="//player.bilibili.com/player.html?aid=968015764&bvid=BV14p4y197Ue&cid=187146193&page=1" scrolling="no" width="600px" height="450px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>


# Steps to set a kalman filter:

## Linear systems:
## Step 1: Build system model
Build the process model (equation 13) 
and the observation model (equation 14).

Through these two models, we know how these two models work.
Plus, we can get process model coefficient **a**, control signal **U_k**, and measurement noise **V_k**.

We will use these coefficients in later steps.

![step1.JPG](https://i.loli.net/2020/05/05/dWJAzFu78eP2rUQ.jpg)

## Step 2: Calculate the predicted state
 ![step2.JPG](https://i.loli.net/2020/05/05/Mmw6rYkpBVUCjRf.jpg)
 By using the state from previous time step (k-1),
 equation (15) calculates **x_k--** the current (time step: k) priori estimate;
 (the hat means estimated value)
 
 equation (16) calculates **p_k--**, the current covariance of this priori estimate.
 
 **But they are just our prediction, we need to use the measured data to refine them to get an optimal result.**  And this is the point of using kalman filter.
 
## Step 3: Update the predicted state 
![step3.JPG](https://i.loli.net/2020/05/05/1o8e9vEuJRYnpys.jpg)
First, in (17), we calculate the kalman gain **g_k** by using predicted covariance **p_k--**.

Then in (18), we update the **x_k** by combining predicted data **x_k--** and measured data **z_k**. 
(The essence of this step is to multiply **x_k--** and **z_k**'s probability density function, for more information, please check the fourth video.)

And in (19), we update the covariance **p_k** too.

## Step 4: Loop
After getting the updated data, we use this set of data, return back to step 2 to calculate the predicted state of next time step. Over and over again.


## Result:

First we need the process model and observation model to get necessary coefficients.

Then we do the prediction.

After that, we update the prediction state by combining predicted data and measured data together.

So, as a result, the updated data **x_k** is what we want, it is more accurate than the predicted-only version. 

And this system is an Iterative system.


## Non-linear: extended kalman filter:
## Step 1: Build system model

![4.JPG](https://i.loli.net/2020/05/05/gpZMFsqU2HVY649.jpg)
## Step 2: Calculate the predicted state
![5.JPG](https://i.loli.net/2020/05/05/IADLqcFiKsSPm6E.jpg)
F_k is the Jacobian matrix of f(xk,uk).
Q is used to refine the system's performance. We can use diagonal matrix at the beginning, and correct it in future according to system's performance.

## Step 3: Update the predicted state 
![6.JPG](https://i.loli.net/2020/05/05/XxrocHGyLihF4jW.jpg)
H_k is the Jacobian matrix of h(xk).

For R,  we can use diagonal matrix too, and then correct it in future according to system's performance.
