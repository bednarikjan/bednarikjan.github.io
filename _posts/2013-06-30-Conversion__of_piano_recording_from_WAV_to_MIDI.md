---
published: false
layout: post
tags: "signal-processing machine-learning WAV MIDI matlab"
date: "2013-06-30 23:51"
thumbnail: "/img/2013-06-30-wav/thumbnail.png"
---

<div class="post">

<p> The aim of the thesis is to propose a system capable of automatic conversion of polyphonic
piano recordings from the audio format WAV to MIDI. The thesis describes problems
related to single tone recognition in music recordings and proposes a solution based on a
probabilistic model that uses the Probabilistic Latent Component Analysis method. Recordings
of isolated digital piano tones were used to train the system. The proposed system was
tested on classical recordings of the Classical Piano MIDI database and on recordings of a
Korg SP-250 piano and evaluated using a variety of metrics. The conclusion part contains
the results of recognition success rate and their comparison with other existing systems.

<!--more-->

<div>
  <a href="/img/2015-04-15-hum_gest_rec/installation.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/installation.png" alt="The sensor installation and the detection region" width="350" align="middle">
  </a>
</div>

<p>One might ask, why to reinvent the whell and not just place the sensor in front of the tracked person and use the already working side-view? The reason is that this system was ordered byt the Czech Republic based glass installations manufacturer Lasvit, who intended to create a kinect installation controled by human gestures in the real-time and who insisted that the (depth) sensor must not interfere with the exposition and must not be seen. Therefore the only possible solution was to place the sensor on the ceiling.</p>

<div>
  <a href="/img/2015-04-15-hum_gest_rec/tracking.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/tracking.png" alt="System architecture" width="650" height="365" align="middle">
  </a>
</div>

<h2>System overview</h2>

<p>The system is capable of detection and tracking a person and currently it can recognize six predefined gestures. The good thing is that no prior knowledge about a person to be tracked is required as the system derives the necessary information autonomously during the human detection phase. Even crowded environments are handled using selective tracking of formerly detected person. We optimised the overall performance with the help of GPU acceleration using CUDA framework and the system is thus capable of running real time.</p>

<h2>How it works?</h2>

<p>The whole system is composed of three main parts: human detection (and learning his/her physiological properties), human tracking and gesture recognition. The most important and the most time consuming part, the tracking, is based on fitting an articulated human body model to obtained data using particle filter framework and specifically defined constraints which originate in physiological properties of the human body. Since the system must evaluate approx. 10000 particles per frame the GPU acceleration was inevitable. The gesture recognition part utilizes the timed automaton conforming to the human body poses and regarding tolerances of the joints positions and time constraints. </p>

<p> We published the paper <a href="http://excel.fit.vutbr.cz/2015/submissions/095/95.pdf">Human gesture recognition using top view depth data obtained from Kinect sensor</a> where we describe the internals of the system in great detail. </p>

<div>
  <a href="/img/2015-04-15-hum_gest_rec/system_architecture.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/system_architecture.png" alt="System architecture" width="450" height="381" align="middle">
  </a>
</div>

<h2>Implementation</h2>

<p>The system is based on the optimized C++ implementation utilizing ROS (Robot Operating System) framework where the most demanding parts of the system were accelerated on GPU using CUDA framework. Furthermore the implementation utilizes OpenCV, PCL and Eigen libraries. </p>

<h2>Real world application</h2>

<p> The system was ordered by the company Lasvit, Czech Republic based designer and manufacturer of the luxury glass installations and lighting collections, and it was presented together with their kinetic lighting system Supernova on <a href="http://salonemilano.it/en-us/EXHIBITORS/Euroluce">Euroluce 2015</a> exhibition held in Milan in April 2015. In the demonstration video below the internals of the system are shown as well as the teaser from Euroluce 2015 made by Lasvit. </p>

<iframe src="https://player.vimeo.com/video/144561041" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> 

<h2>Awards</h2>
<p>I had the chance to present the project at conference <a href="http://excel.fit.vutbr.cz/">Excel@FIT 2015</a>, student competition conference of innovations, technology and science in IT, which was held by hthe Faculty of Information Technology, Brno University of Technology on 30th April 2015. Our project was awarded the 1st prize for the excellent idea, the 2nd prize for the innovation potential, the 3rd prize for the business potential and the 4th prize for the social contribution.</p>

<h2>Authors</h2>
<ul>
<li><a href="mailto:jan.bednarik@hotmail.cz">Jan Bednařík</a></li>
<li><a href="mailto:david.herman@rcesystems.cz">David Herman</a></li>
</ul>
<p>I worked on this project together with my colleague David Herman as an employee of the Czech Republic based tech company <a href="http://www.rcesystems.cz/">RCE systems.</a></p>

<h2>Project materials</h2>

<table>
  <col width="6%">
  <col width="12%">
  <tr>
    <td><img src="/img/pdf.png" alt="pdf icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Paper (EN):</span></td>
    <td><a href="http://excel.fit.vutbr.cz/2015/submissions/095/95.pdf">Human gesture recognition using top view depth data obtained from Kinect sensor</a></td>
  </tr>
</table>

</div>
