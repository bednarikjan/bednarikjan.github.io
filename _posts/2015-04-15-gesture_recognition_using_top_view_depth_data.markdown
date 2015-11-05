---
layout: post
title: Gesture recognition using top view depth data
subtitle: ""
date: {2015-04-13}
author: Jan Bednarik
"header-img": img/human_gesture_recognition_header.png
published: true
---

<p>The visual tracking of human body and gesture recognition represent a key technology in a number of areas such as video surveillance, security applications, entertainment industry or natural human-machine interaction. With the advent of depth sensors capable of 3D scene reconstruction the reliability of human tracking solutions increased. Most of the current approaches rely on the side view mounted sensors, i.e. a standing person must directly face the sensor, however certain applications might require the sensor to be placed away from the scene which the user moves within. For one of our partners we developed and implemented a system suitable for real-time human tracking and predefined human gestures recognition using depth data acquired from Microsoft Kinect sensor installed right above the detection region.</p>

<h2>System overview</h2>

<p>The system is capable of reliable detection and tracking of a person and it supports recognition of predefined gestures. No prior knowledge about a person to be tracked is required as the system derives all the necessary information autonomously during the human detection phase. Furthermore even crowded environments pose no limitations to the system’s performance as the selective tracking of formerly detected person is implemented. Thorough tests incorporating multiple subjects with different body heights and shapes were performed. High precision was achieved exceeding 92 % and thanks to the optimized C++ implementation together with GPU acceleration using CUDA framework the system runs in real-time (reaching more then 30 FPS). These results make the system perfectly suitable for the real time applications.</p>
<p>
  <img src="img/system_architecture.png" alt="System architecture" width="450" height="381" />
</p>

<h2>Implementation</h2>

<p>The system is based on the optimized C++ implementation utilizing ROS (Robot Operating System) framework where the most demanding part of the system were accelerated on GPU using CUDA framework.</p>

<iframe src="https://player.vimeo.com/video/144561041" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="https://vimeo.com/144561041">Human gesture recognition using top view depth data</a> from <a href="https://vimeo.com/user34095639">J B</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
