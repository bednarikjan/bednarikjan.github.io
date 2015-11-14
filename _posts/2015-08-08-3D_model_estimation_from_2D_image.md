---
published: false
layout: post
tags: "computer-vision multiple-view-geometry object-reconstruction C++"
date: "2015-08-08 17:01"
thumbnail: "/img/2015-08-08-3D_object_from_2D/thumbnail.png"
title: Reconstruciotn of 3D models from 2D images
---


<div class="post">

<p>
In this project I attempted to create an application which would enable the user to reconstruct simple block-shaped objects together with their position in the 3D world from 2D images of the scene. The user is only required to draw 3 or 4 points specifying one base of the object while the volume and the position could then be easily derived as the user stretches the rendered object (to match the underlying image). Multiple view geometry as well as the marker(s) is used here to compute the homography between the image and world frame.
</p>

<!--more-->

<div>
  <a href="/img/2015-06-05-traj_clus/trajclus.png">
  <img class="post" src="/img/2015-06-05-traj_clus/trajclus.png" alt="The sensor installation and the detection region" width="700" align="middle">
  </a>
</div>

<h2>System overview</h2>

<p>
</p>

<h2>How it works?</h2>

<p>

<h2>Implementation</h2>

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

