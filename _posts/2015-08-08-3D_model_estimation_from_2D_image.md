---
published: true
layout: post
tags: "computer-vision multiple-view-geometry object-reconstruction C++"
date: "2015-08-08 17:01"
thumbnail: "/img/2015-08-08-3D_object_from_2D/thumnbnail.png"
title: Reconstruction of 3D models from 2D images
---



<div class="post">

<p>
In this project I attempted to create an application which would enable the user to reconstruct simple block-shaped objects together with their position in the 3D world from 2D images of the scene. The user is only required to draw 3 or 4 points specifying one base of the object while the volume and the position could then be easily derived as the user stretches the rendered object (to match the underlying image). Multiple view geometry as well as the marker(s) are used here to compute the homography between the image and the world frame.
</p>

<!--more-->

<div>
  <a href="/img/2015-08-08-3D_object_from_2D/table.png">
  <img class="post" src="/img/2015-08-08-3D_object_from_2D/table.png" alt="The sensor installation and the detection region" width="600" align="middle">
  </a>
</div>

<h2>System overview</h2>
<p>
A couple of camera images of the scene taken from the different locations is required while all of the images must contain a chessboard printed on the paper placed somewhere in the scene. The application then allows you to draw four arbitrarily placed points in the scene and then visually define the object volume. Multiple objects can be drawn in one image.
</p>

<h2>How it works</h2>
Since we have multiple images of the scene including a printed chessboard, it is possible to calculate both the camera intrinsic and extrinsic matrices. As the next step the world -> camera frame transformation matrix is computed. Since the chesboard serves the purpose of the marker here and defines an XY plane (Z = 0) it is possible to compute the homography between the world plane and the image. Using the inverse homography matrix we finally obtain the coordinates of the object vertices in the 3D scene.
<p>

<h2>Implementation</h2>
The demo application is implemented in C++ and uses the OpenCV library. You cand draw the points using the left mouse button and further adjust the object volume using the up and down keys (see the video below).

<iframe src="https://player.vimeo.com/video/145732353" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<h2>Authors</h2>
<ul>
<li><a href="mailto:jan.bednarik@hotmail.cz">Jan Bednařík</a></li>
</ul>
<p>I worked on this project as an employee of the Czech Republic based company <a href="http://www.rcesystems.cz/">RCE systems.</a></p>

<h2>Project materials</h2>

<table>
  <col width="6%">
  <col width="12%">
  <tr>
    <td><img src="/img/source.png" alt="source code icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Source code (C++):</span></td>
    <td><a href="https://github.com/bednarikjan/3DObjectReconstruction">3D model reconstruction</a></td>
  </tr>
</table>

</div>
