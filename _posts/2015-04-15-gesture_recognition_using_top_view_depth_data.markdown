---
layout: post
title: Gesture recognition using top view depth data
subtitle: ""
date: {2015-04-13}
author: Jan Bednarik
"header-img": img/human_gesture_recognition_header.png
published: true
---

<p> In this project I worked on a system capable of tracking a human and detecting human gestures using depth data from Microsoft Kinect sensor placed right above the detection region. Of course, the advent of affordable depth sensors enabling for the 3D scene reconstruction gave rise to the multiple already working SW solutions for human tracking (e.g. Microsoft for Kinect SDK, OpenNI etc.), nevertheless neither of these libraries support human recognition and tracking when the sensor is placed right above the tracked person. Here the real challenge started as we had to design and implement the human recognition, tracking and gesture detection from scratch. </p>

<p>One might ask, why to reinvent the whell and not just place the sensor in front of the tracked person and use the already working side-view? The reason is that this system was ordered byt the Czech Republic based luxury glass installations and lighting collections manufacturer Lasvit, who intended to create a kinect installation controled by human gestures in real-time, where the used (depth) sensor must not interfere with teh exposition and must not be seen. Therefore the only possible solution was to place the sensor on the ceiling.</p>

<div>
  <a href="/img/2015-04-15-hum_gest_rec/tracking.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/tracking.png" alt="System architecture" width="650" height="365" align="middle">
  </a>
</div>

<h2>System overview</h2>

<p>The system is capable of detection and tracking a person and it supports recognition of six predefined gestures. The good thing is that no prior knowledge about a person to be tracked is required as the system derives the necessary information autonomously during the human detection phase. Even crowded environments is handled using selective tracking of formerly detected person. We optimised the overall performance with the help of GPU acceleration using CUDA framework and the system is thus capable of running real time.</p>

<h3>How it works?</h3>

<p>The whole system is composed of three main parts: human detection (and learning his/her physiological properties), human tracking and gesture recognition. For the big picture of the main system blocks see the figure below. The most important and the most time consuming part, the tracking, is based on fitting an articulated human body model to obtained data using particle filter framework and specifically defined constraints which originate in physiological properties of the human body. The gesture recognition part utilizes the timed automaton conforming to the human body poses and regarding tolerances of the joints positions and time constraints. </p>

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
