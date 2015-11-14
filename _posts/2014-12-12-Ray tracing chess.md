---
layout: post
tags: "computer-graphics ray-tracing 3d-model C++"
date: "2014-12-02 18:45"
thumbnail: "/img/2014-12-02--ray_tracing/thumbnail.png"
title: Chess renderer using ray tracing
published: true
---



<div class="post">

<p>
This project was the main deliverable of the winter semester course Computer graphics. Even though the principle of ray tracing is not particuralry new and is already well established, I have somehow always felt the temptation to write my own simple ray tracer from scratch. Therefore, together with my colleague, we decided to assign for a project called Chess rendered using ray tracing. The resulting application written in C++ is capable of rendering the chessboard with arbitrarily placed pieces, it uses the Phong shading model and supports shadows and reflections. Hooray, one programmer's dream checked :-).
</p>

<!--more-->
 
<h2>System overview</h2>
 
 The resulting application lets the user render the scene containing the chessboard covered by pieces of both opponets. We decided to make the system as parametrizable as possible. It is possible to set the camera's resolution and FOV, the position of the light in the scene, background color, recursion depth of ray tracing, the colors of the pieces and chessboard fields as well as the reflectance and the shininess. Regarding the chessboard model, the user can set the position of each piece. Both the renderer and the model configuration can be done using the files <tt>configChessDefault</tt> and <tt>configRTDefault</tt> (see the <a href="">source code</a>).
 
<h2>Implementation</h2>
<p>To reinvent the wheel was the approach we went for :-). As a nice practice we implemented everything from scratch using pure C++ (we only use the Eigen library for camera transformations). As the computation of the intersections with the model's triangles represents the most significant bottleneck of the application, we implemented  In order to optimize the algorithm we implemented the method Fast Minimum Storage Ray/Triangle Intersection (see <a href="http://dl.acm.org/citation.cfm?id=272315">this paper</a>). It was also necessary to introduce bounding boxes otherwise the renderer would be dead-slow.
</p>
 
<h2>Project materials</h2>
 
<table>
  <col width="6%">
  <col width="12%">
  <tr>
    <td><img src="/img/source.png" alt="source code icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Source code (C++):</span></td>
    <td><a href="https://github.com/bednarikjan/RayTracingChess/tree/master/rtchess">Chess renderer using ray tracing</a></td>
  </tr>
  <tr>
    <td><img src="/img/pdf.png" alt="pdf icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Doc (CZ):</span></td>
    <td><a href="">Documentation - Ray tracing</a></td>
  </tr>
</table>
 
<h2>Gallery</h2>
 
 <div>
  <a href="/img/2014-12-02--ray_tracing/01.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/01.png" alt="Ray traced chess 01" width="700" align="middle">
  </a>
</div>

<div>
  <a href="/img/2014-12-02--ray_tracing/02.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/02.png" alt="Ray traced chess 02" width="700" align="middle">
  </a>
</div>

<div>
  <a href="/img/2014-12-02--ray_tracing/03.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/03.png" alt="Ray traced chess 03" width="700" align="middle">
  </a>
</div>

<div>
  <a href="/img/2014-12-02--ray_tracing/04.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/04.png" alt="Ray traced chess 04" width="700" align="middle">
  </a>
</div>

<div>
  <a href="/img/2014-12-02--ray_tracing/05.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/05.png" alt="Ray traced chess 05" width="700" align="middle">
  </a>
</div>

<div>
  <a href="/img/2014-12-02--ray_tracing/06.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/06.png" alt="Ray traced chess 06" width="700" align="middle">
  </a>
</div>


<div>
  <a href="/img/2014-12-02--ray_tracing/07.png">
  <img style="margin: 10px 10px;" class="post" src="/img/2014-12-02--ray_tracing/07.png" alt="Ray traced chess 07" width="700" align="middle">
  </a>
</div>
 
</div>
