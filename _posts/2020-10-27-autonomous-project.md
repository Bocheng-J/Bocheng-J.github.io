---
layout:     post
title:      Autonomous car project demonstration
subtitle:   Design of a self-driving car
date:       2020-10-27
author:     oscar
header-img: img/post_0527_bacground.jpg
catalog: true
tags:
    - project demonstration
    - study notes
---


# 1. Project introduction 
The purpose of this project is to design one self-driving car, which can drive in the special track without hitting any cone.


The track is formed by three kinds of different cones:

**Blue cone** represents the right side of the track

**Yellow cone** represents the left side of the track

**Red cone** represents the start/end of the track

# 2. Implementation
The autonomous car uses camera as the input sensor, by applying Opencv algorithm to find color and contour of the cones, we can recognize blue cones and yellow cones.

After getting blue cones and yellow cones, we can find the middle point of the track, and set that point as the aim point, where we want our car to drive to. 

By calculating the angle between aim point and current car point, we can get the steering angle, sending this angle to motor block, the car can be controlled autonomously.

The total project is built based on docker, using microservices. So we can achieve cross-compilation inside our system.


# 3. Simulation video
<iframe src="//player.bilibili.com/player.html?aid=370853141&bvid=BV1KZ4y1W73F&cid=194873648&page=1" scrolling="no" width="100%" height="450px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

As seen in video, the car can self-drive in the track without hitting any cones.
