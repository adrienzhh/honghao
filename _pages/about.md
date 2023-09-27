---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a second-year master student at Carnegie Mellon University working in [Robomechanic lab](https://www.cmu.edu/me/robomechanicslab/), advised by Dr. [Aaron Johnson](https://www.andrew.cmu.edu/user/amj1/). My research foucs on SLAM and perpcetion, especially challenge outside environments 🤖 

I have previsouly obtained by B.S. degrees from Georgia Institute of Technology. I was advised by Dr. [Frank Dellaert](https://dellaert.github.io/). There, I was involved in robotic painting 🎨 using Franka Panda arm 🦾 

My full [CV](https://adrienzhh.github.io/honghao/files/CV-1.pdf)
 
## Publication

<div style="display: flex; flex-direction: row;">
    <img src="images/intro.png" alt="Image" style="width: 25%;" />
    <div style="flex: 1; padding-left: 20px;">
        <p>Your description goes here. This is where you can provide details about the image or any other content you want to describe on the right side.</p>
    </div>
</div>

  <tr onmouseout="db3d_stop()" onmouseover="db3d_start()">
    <td style="padding:20px;width:25%;vertical-align:middle">
      <div class="one">
        <div class="two" id='db3d_image'><video  width=100% height=100% muted autoplay loop>
        <source src="images/owl.mp4" type="video/mp4">
        Your browser does not support the video tag.
        </video></div>
        <img src='images/intro.png' width="160">
      </div>
      <script type="text/javascript">
        function db3d_start() {
          document.getElementById('db3d_image').style.opacity = "1";
        }

        function db3d_stop() {
          document.getElementById('db3d_image').style.opacity = "0";
        }
        db3d_stop()
      </script>
    </td>
    <td style="padding:20px;width:75%;vertical-align:middle">
      <a href="https://dreambooth3d.github.io/">
        <span class="papertitle">DreamBooth3D: Subject-Driven Text-to-3D Generation</span>
      </a>
      <br>
      
  <a href="https://amitraj93.github.io/">Amit Raj</a>, <a href="https://www.linkedin.com/in/srinivas-kaza-64223b74">Srinivas Kaza</a>, <a href="https://poolio.github.io/">Ben Poole</a>, <a href="https://m-niemeyer.github.io/">Michael Niemeyer</a>, <a href="https://natanielruiz.github.io/">Nataniel Ruiz</a>, 
  <a href="https://bmild.github.io/">Ben Mildenhall</a>, <a href="https://scholar.google.com/citations?user=I2qheksAAAAJ">Shiran Zada</a>, <a href="https://kfiraberman.github.io/">Kfir Aberman</a>, <a href="http://people.csail.mit.edu/mrub/">Michael Rubinstein</a>, 
          <strong>Jonathan T. Barron</strong>, <a href="http://people.csail.mit.edu/yzli/">Yuanzhen Li</a>, <a href="https://varunjampani.github.io/">Varun Jampani</a>
          <br>
          <em>ICCV</em>, 2023
          <br>
          <a href="https://dreambooth3d.github.io/">project page</a> / 
          <a href="https://arxiv.org/abs/2303.13508">arXiv</a>
          <p></p>
          <p>Combining DreamBooth (personalized text-to-image) and DreamFusion (text-to-3D) yields high-quality, subject-specific 3D assets with text-driven modifications</p>
        </td>
   </tr>