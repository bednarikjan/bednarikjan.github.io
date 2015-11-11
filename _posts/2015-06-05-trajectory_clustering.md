---
layout: post
tags: "machine-learning unsupervised-learning clustering Python"
date: "2015-06-05 13:18"
thumbnail: "/img/2015-06-05-traj_clus/thumbnail.png"
title: Trajectory clustering
published: true
---

<div class="post">

<p> Automatic trajectory clustering is particularly useful in projects where a huge amount of spatio temporal data must be handeled. It might be ecologists who track wild animals, meteorologists who track hurricane flows or traffic researchers who analyse the common patterns in traffic - they all work with tons od data wchich must be (auomatically) analyzed in order to derive meaningful information. Thus this project focuses on implementing algorithms capable of fully automatic clustering of 2D trajectories. </p>

<!--more-->

<div>
  <a href="/img/2015-06-05-traj_clus/trajclus.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/installation.png" alt="The sensor installation and the detection region" width="350" align="middle">
  </a>
</div>

<h2>System overview</h2>

<p>
The demo application allows you to draw your own trajectories (on the top-view photo of roundabout) and then let the system cluster them. In case of agglomerative clustering implementation you must specify the expected number of clusters, wheras the spectral clustering method is smarter and is capable of estimating the most appropriate number of clusters itself.
</p>

<h2>How it works?</h2>

<p>
The system is based on the modified Hausdorff distance used as a semi-metric to define the similarity measure (affinity) among different trajectories. The modification of the Hausdorff distance is necessary to alleviate the imprecision of the trackers producing the trajectories. As for the clustering part, either the agglomerative or the spectral clustering can be used. 

The main advantage of the spectral clustering is its ability to find the number of clusters itself. Basically first the normalized affinity matrix is created which is then eigen-decomposed end the eigen-values are examined. The number of eigen-values exceedeing the given threshold specifies the maximum number of clusters. The clustering itself might be done using standard K-means approach (where each eigen-vector represents one datum) for all possible number of clusters. The final number of clusters is chosen according to the distortion score obtained for each clustering attempt. For more details see the paper <a href="https://www.google.cz/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0CCUQFjAAahUKEwjPmvixuYnJAhWJ0RQKHf1QBMQ&url=http%3A%2F%2Fieeexplore.ieee.org%2Fxpls%2Fabs_all.jsp%3Farnumber%3D5462900&usg=AFQjCNGDZf7nnVD_EuvviQTQOdHtLIeM3A&sig2=0_SachOr4f8vFdW8aF0JZg">Clustering of vehicle trajectories</a>.</p>

<h2>Implementation</h2>

The demo app is implemented in Python and utilizes NumPy and SciPy libraries. I made no optimizations as this app was meant as the prototype of the chosen approach.

<h2>Real world application</h2>

<p>I worked on this project as an employee of the Czech Republic based tech company <a href="http://www.rcesystems.cz/">RCE systems</a> which develops the system <a href="http://datafromsky.com/">DataFromSky</a> - a specialized solution for automatic analysis of traffic activity in aerial videos. The trajectory clustering was used as a subsystem enabling the researchers to perform the analyses showing the common trends in the traffic. For more info see this <a href="http://datafromsky.com/news/new-functionality-flow-visualization/">blog post</a>.</p>

<div>
  <a href="/img/2015-06-05-traj_clus/dfs_trajclus.png">
  <img class="post" src="/img/2015-04-15-hum_gest_rec/installation.png" alt="The sensor installation and the detection region" width="350" align="middle">
  </a>
</div>

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

</div>

