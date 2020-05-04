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

<video src="https://vdn3.vzuu.com/SD/v3_22cf47c0-e288-11e9-a5c8-f6c3b9ad3fcc.mp4?disable_local_cache=1&bu=http-com&expiration=1588626131&auth_key=1588626131-0-0-e8ec34258436d05e2acdb2be81c6ab3b&f=mp4&v=tx"></video>

## 2. State Observers:

<video src="https://vdn3.vzuu.com/SD/v3_462b3fe4-e288-11e9-8eec-0a15e95faed4.mp4?disable_local_cache=1&bu=http-com&expiration=1588619214&auth_key=1588619214-0-0-bbead69d01354bec004e21e3e191c886&f=mp4&v=tx" width="600px" height="450px" controls="controls"></video>

## 3. Optimal State Estimator:

<video src="https://vdn3.vzuu.com/SD/v3_06d8f1e2-e35a-11e9-97d7-0ac945157a92.mp4?disable_local_cache=1&bu=http-com&expiration=1588619262&auth_key=1588619262-0-0-445dc726fa1fa71fa7bf72a549874595&f=mp4&v=tx" width="600px" height="450px" controls="controls"></video>

## 4. Optimal State Estimator Algorithm:

<video src="https://vdn3.vzuu.com/SD/v3_170e4586-e426-11e9-9a35-6e0fb3749454.mp4?disable_local_cache=1&bu=http-com&expiration=1588619263&auth_key=1588619263-0-0-1dfd0b8384b197e122541e9b23109c40&f=mp4&v=tx" width="600px" height="450px" controls="controls"></video>

## 5. Nonlinear State Estimators:

<video src="https://vdn3.vzuu.com/SD/v3_9c9077ee-e4f1-11e9-a5a9-727d3207a1f2.mp4?disable_local_cache=1&bu=http-com&expiration=1588619332&auth_key=1588619332-0-0-bf4c301dc058a9b4c06cf2a9611362da&f=mp4&v=tx" width="600px" height="450px" controls="controls"></video>

## 6. How to Use a Kalman Filter in Simulink:

<video src="https://vdn3.vzuu.com/SD/v3_be17418c-e5c7-11e9-9c63-fe4dd367aa36.mp4?disable_local_cache=1&bu=http-com&expiration=1588619440&auth_key=1588619440-0-0-f46ecb4b7abb50d7a8aeec56b3c99c7c&f=mp4&v=tx" width="600px" height="450px" controls="controls"></video>

## 7. How to Use an Extended Kalman FIlter in SImulink:

<video src="https://vdn3.vzuu.com/SD/v3_3f701e28-e6a1-11e9-85b1-f63f25bc9388.mp4?disable_local_cache=1&bu=http-com&expiration=1588619441&auth_key=1588619441-0-0-a786d515a007e84c61fbc01c701d0cef&f=mp4&v=tx" width="600px" height="450px" controls="controls"></video>

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
