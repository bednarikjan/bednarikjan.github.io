---
layout: post
title: Gesture recognition using top view depth data
subtitle: ""
date: {2015-04-13}
author: Jan Bednarik
"header-img": img/human_gesture_recognition_header.png
published: true
---

<p>The visual tracking of human body and gesture recognition represent a key technology in a number of areas such as video surveillance, security applications, entertainment industry or natural human-machine interaction. With the advent of depth sensors capable of 3D scene reconstruction the reliability of human tracking solutions increased. Most of the current approaches rely on the side view mounted sensors, i.e. a standing person must directly face the sensor, however certain applications might require the sensor to be placed away from the scene which the user moves within. Therefore we developed and implemented a system suitable for real-time human tracking and predefined human gestures recognition using depth data acquired from Microsoft Kinect sensor installed right above the detection region.</p>

<div>
  <a href="/img/2015-04-15-hum_gest_rec/tracking.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/tracking.png" alt="System architecture" width="650" height="365" align="middle">
  </a>
</div>

<h2>System overview</h2>

<p>The system is capable of reliable detection and tracking of a person and it supports recognition of predefined gestures. No prior knowledge about a person to be tracked is required as the system derives all the necessary information autonomously during the human detection phase. Furthermore even crowded environments pose no limitations to the system’s performance as the selective tracking of formerly detected person is implemented. Thorough tests incorporating multiple subjects with different body heights and shapes were performed. High precision was achieved exceeding 92 % and thanks to the optimized C++ implementation together with GPU acceleration using CUDA framework the system runs in real-time (reaching more then 30 FPS). These results make the system perfectly suitable for the real time applications.</p>

<div>
  <a href="/img/2015-04-15-hum_gest_rec/system_architecture.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/system_architecture.png" alt="System architecture" width="450" height="381" align="middle">
  </a>
</div>


<h2>Implementation</h2>

<p>The system is based on the optimized C++ implementation utilizing ROS (Robot Operating System) framework where the most demanding part of the system were accelerated on GPU using CUDA framework.</p>

<h2>Real world application</h2>

The system was accepted as the entertainment solution enabling a user to control a glass kinetic installation which was exhibited by the Czech Republic based luxury glass installations and lighting collections manufacturer Lasvit on this year’s Euroluce 2015 exhibition held in Milan in April 2015. Below you can watch a video which shows the internal of the system and includes the teaser from Euroluce 2015 made by Lasvit.

<iframe src="https://player.vimeo.com/video/144561041" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="https://vimeo.com/144561041">Human gesture recognition using top view depth data</a> from <a href="https://vimeo.com/user34095639">J B</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
