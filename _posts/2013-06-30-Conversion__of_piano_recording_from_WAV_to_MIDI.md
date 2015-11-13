---
published: false
layout: post
tags: "signal-processing machine-learning WAV MIDI matlab"
date: "2013-06-30 23:51"
thumbnail: "/img/2013-06-30-wav/thumbnail.png"
---


<div class="post">

<p> During the last year of the Bachelor's programme we were to choose a topic for our Bachelor thesis. As I found myself quite interested in signal processing and as I wanted to somehow link the schoolwork with music I decided to propose a topic which would focus on automatic transcription of piano recording to piano sheets (or at least MIDI). The resulting application written in Matlab is capable of analyzing the piano recording and transforming it to the MIDI transcription.
</p>

<!--more-->

<p>
Here is the abstract of the thesis:
<span style="font-style: italic;">The aim of the thesis is to propose a system capable of automatic conversion of polyphonic piano recordings from the audio format WAV to MIDI. The thesis describes problems related to single tone recognition in music recordings and proposes a solution based on a probabilistic model that uses the Probabilistic Latent Component Analysis method. Recordings of isolated digital piano tones were used to train the system. The proposed system was tested on classical recordings of the Classical Piano MIDI database and on recordings of a Korg SP-250 piano and evaluated using a variety of metrics. The conclusion part contains the results of recognition success rate and their comparison with other existing systems.</span>
</p>

<h2>System overview</h2>
The 

<h2>How it works?</h2>
One of the main requirements was to support polypohny, as that poses a real challenge (nowadays the systems focusing on single pitch detection work pretty well). I decided to utilize the PLCA approach, a probabilistic method which is able to decompose the N-dimensional data structure to the arbitrary number of one-deimsnional bases. I trained each basis both using the recordings of the real piano and the synthetitc sounds (think of a base as one piano key). PLCA proved to be capable of distinguisingh among separate key strokes even when polypohny was in place. In exepriments the system achieved the precision of nearly 74 % which is moreless (depending on the dataset) on par with other state-of-the-art systems. Though it is still not robust enought for fully automatic music transcription as for the perception by a musician the resulting MIDI sounds close enough to the original signal.

<div>
  <a href="/img/2013-06-30-wav2midi/notes.png">
  <img class="post" src="/img/2013-06-30-wav2midi/notes.png" alt="Polyphony" width="600" align="middle">
  </a>
</div>

<div>
  <a href="/img/2013-06-30-wav2midi/spectrogram.png">
  <img class="post" src="/img/2013-06-30-wav2midi/spectrogram.png" alt="Spectrogram for a few seconds of Smoke on the water song played on piano." width="600" align="middle">
  </a>
</div>

<h2>Implementation</h2>
<p>The system is implemented in Matlab and can be used as a command line application accpeting the WAV recording and producing the correspondent MIDI.</p>

<h2>Awards</h2>
<p>The Bachelor thesis was awarded the Dean's award for outstanding Bachelor thesis.</p>

<h2>Project materials</h2>

<table>
  <col width="6%">
  <col width="12%">
  <tr>
    <td><img src="/img/source.png" alt="source code icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Source code (Matlab):</span></td>
    <td><a href="https://github.com/bednarikjan/WAV2MIDI">WAV2MIDI</a></td>
  </tr>
  <tr>
    <td><img src="/img/pdf.png" alt="pdf icon" width="40" height="40" align="middle"></td>
    <td><span style="font-variant: small-caps;">Bachelor thesis (CZ):</span></td>
    <td><a href="http://excel.fit.vutbr.cz/2015/submissions/095/95.pdf">Conversion of piano recording from WAV to MIDI</a></td>
  </tr>
</table>

</div>
