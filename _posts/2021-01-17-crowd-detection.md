---
type: posts
title:  "Crowd detection using fractal dimension and local density"
classes: wide
tags: [image processing, crowd detection, fractal dimension, local density]
toc: false
---

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

In this post, I will present my works on crowd detection. Crowd detection is the task of classifying and localizing crowd in images (see Fig. 1). In this work, I am particularly interested in pedestrians crowd detection. I mostly used image processing methods to isolate the crowd from non-interesting objetcs and background. Specifically, the classification task is based on fractal dimension and the localization task is based on local density.

<p align="center">
  <img width="450" height="250"  src="/assets/images/crowd_detection/crowd_detection_ex_pred.png">
  <br>
  Figure 1:  Example of crowd detection using my model.
</p>


According to Google Scholar, 1460 papers have been up to now published concerning crowd detection. There are a myriad of areas where crowd detection intervenes. The figure below shows some of theses areas.

In 

<p align="center">
  <img width="754" height="140" src="/assets/images/crowd_detection/crowd_detection_app.png">
  <br>
  Figure 2:  Application of crowd detection in different areas.
</p>


Imagine you are a self-driving car going on your merry way along a road: within all the sensors that help the computer build a representation of the outside world, an essential part will be cameras. For each frame, the car will need to evaluate where the road is, any street sign or light, and finally if there are any obstacles on its way (people, bicycles, walls, other cars). This is where [semantic segmentation](https://en.wikipedia.org/wiki/Image_segmentation) comes in: the goal is to classify every pixel in the image as representing a certain class (e.g., person, car, street, sidewalk, speed limit, etc...).

# Conclusions
The proposed model is still far from saturating the benchmark metrics. If complicated background are crossed, the model may miss  targets or may provide an imprecise bounding box. However, the model is based only on image processing methods for the task of crowd detection. In addition, no intelligence is behind the established process. 


You can access the complete code via [GitHub gist](https://github.com/AsmaBRZ/Crowd-detection).
