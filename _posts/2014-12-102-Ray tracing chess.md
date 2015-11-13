---
published: false
---


<div class="post">

<p>
This project was the main deliverable of the winter semester course Computer graphics. Even though the principle of ray tracing is not particuralry new and is already well established, I have somehow always felt the temptation to write my own simple ray tracer from scratch. Therefore, together with my colleague, we decided to assign for a project called Chess rendered using ray tracing. The resulting application written in C++ is capable of rendering the chessboard with arbitrarily placed pieces, it uses the Phong shading model and supports shades and reflections. Hooray, one programer's dream checked.
</p>

<!--more-->

<div>
  <a href="/img/2015-06-05-traj_clus/trajclus.png">
  <img class="post" src="/img/2015-06-05-traj_clus/trajclus.png" alt="The sensor installation and the detection region" width="700" align="middle">
  </a>
</div>
 
<h2>System overview</h2>
 
 The resulting application lets the user render the scene containing the chessboard covered by pieces of both opponets. We decided to make the system as parametrizable as possible. It is possible to set the camera's resolution and FOV, the position of the light in the scene, background color, recursion depth of ray tracing, the colors of the pieces and chessboard fields as well as the reflectance and the shininess. Regarding the chessboard model, the user can set the position of each piece. Both the renderer and the model configuration can be done using the files <tt>configChessDefault</tt> and <tt>configRTDefault</tt> (see the source code).
 
<p>
</p>
 
<h2>How it works?</h2>
 
<p>
</p>
 
<h2>Implementation</h2>
 
<h2>Project materials</h2>
 
<table>
  <col width="6%">
  <col width="12%">
  <tr>
    <td><img src="/img/source.png" alt="source code icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Source code (Python):</span></td>
    <td><a href="https://github.com/bednarikjan/TrajectoryClustering">Trajetory clustering</a></td>
  </tr>
</table>
 
<h2>Gallery</h2>
 
</div>