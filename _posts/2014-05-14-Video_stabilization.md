---
layout: post
tags: "image processing computer-vision video-stabilization C++"
date: "2014-05-14 10:17"
thumbnail: "/img/2014-05-14-vid_stab/thumbnail.png"
title: Video stabilization
published: true
---


<div class="post">

<p> Thanks to the course <emph>Image processing</emph> run by my faculty during summer semester 2014/2015 I got the chance to choose among a couple of tempting projects to work on during the semestr. As I had been impressed by the Google's new approach for stabilizing videos, which they eventually embedded as an internal tool to the YouTube portal, I had decided to assign for a project with a single requirement - design and implement the tool for video stabilization. The resulting tool written in C++ implements two different methods and achieves pretty interesting results.</p>

<!--more-->

<p>
The resulting program is a command line tool working as a filter. It reads the input video and produces its stabilized equivalent. When using the tool you can fine-tune multiple parameters specific to the chosen method. The tool is implemented in C++ and uses the OpenCV library.
</p>

<h2>How it works?</h2>

<p>
The first method, Gray Coded Bit Plane Matching, compares the bit fields in the consecutive frames of the video and tries to estimate the most likely translation. A bitfield is a matrix obtained from the input frame by iteratively applying the XOR operation (for more details see the paper <a href="http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.123.6888&rep=rep1&type=pdf">Real-Time Digital Image Stabilization</a>). The method is fast but only enables for translation correction.
</p>

<p>
The second method utilizes the KLT tracker for detection and tracking of the key points. As the key points are gradually lost (the camera/object moves) it is necessary to reinitialize the tracker. In order to reduce the computational complexity we only reinitialize the tracker if the number of tracked points falls below the specifed threshold. The affine transformation itslef is then estimated using Singular Value Decompostion which gives us the rotation and translation matrix. Thus this method allows for compansating both rotation and translation.
</p>

<p>
Furthermore we took the incpiration in the Google's approach described in <a href="http://static.googleusercontent.com/media/research.google.com/cs//pubs/archive/37041.pdf">this paper</a> and implemented the quazi-simulation of the long term camera motion. We only support the linear motion model.
</p>

<br>

<p><strong>Video stabilization using KLT and SVD:</strong></p>
<iframe src="https://player.vimeo.com/video/145458594" width="500" height="375" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<p><strong>Video stabilization using Gray Coded Bitplane Matching:</strong></p>
<iframe src="https://player.vimeo.com/video/145456516" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<h2>Authors</h2>
<ul>
<li><a href="mailto:jan.bednarik@hotmail.cz">Jan Bednařík</a></li>
<li><a href="mailto:kvitajakub@gmail.com ">Jakub Kvita</a></li>
</ul>

<h2>Project materials</h2>

<table>
  <col width="6%">
  <col width="12%">
  <tr>
    <td><img src="/img/source.png" alt="source code icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Source code (C++):</span></td>
    <td><a href="https://github.com/bednarikjan/VideoStabilization">Video Stabilization</a></td>
  </tr>
  <tr>
    <td><img src="/img/pdf.png" alt="doc icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Doc (CZ):</span></td>
    <td><a href="https://github.com/bednarikjan/VideoStabilization/blob/master/doc/dokumentace.pdf">Project documentation</a></td>
  </tr>
</table>

</div>
