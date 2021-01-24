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

In this post, I will present my university project on crowd detection. Crowd detection is the task of classifying and localizing crowd in images (see Fig. 1). In this project, I am particularly interested in pedestrians crowd detection. I mostly used image processing methods to isolate the crowd from non-interesting objetcs and background. Specifically, the classification task is based on fractal dimension and the localization task is based on local density.

<p align="center">
  <img width="450" height="250"  src="/assets/images/crowd_detection/crowd_detection_ex_pred.png">
  <br>
  Figure 1:  Example of crowd detection using my model.
</p>

## 1. Applications of crowd detection
According to Google Scholar, 1460 papers have been published concerning crowd detection at this day. There are a myriad of areas where crowd detection is useful [3]. The figure Fig. 2 shows some of these areas.


Thanks to the amazing progress of technology in the medical field, cancer patients can  more and more be saved. Detecting a certain number of cancerous cells, thus forming a crowd, may help for an early-stage diagnosis.

Disaster management generally concerns overcrowding scenarios such as music events. If any panic breaks out among a crowd of thousands of persons, their lives are definitely in danger. Detect overcrowded areas as earlier as possible may avoid the worst scenario.

In addition, crowd detection enables  safety and monitoring procedures to be automated. It can be very helpful to detect anomalies  and thereby predict risks. 

Moreover, crowd detection is valuable for public event management. The supervisory authorities will receive a notification as soon as a public demonstration occures. Therfore, this will greatly assist them to restore calm and order.

Another significant case where crowd detection can be relevant comes to track suspicious activity. For instance, people who are fighting necessarily attract other people and this may exacerbate the situation. So, with crowd detection the security officials receive information regarding suspicious activity in the area, and thus can rapidly intervene.

<p align="center">
  <img width="754" height="140" src="/assets/images/crowd_detection/crowd_detection_app.png">
  <br>
  Figure 2:  Applications of crowd detection in different areas.
</p>


## 2. Model architecture
In this section, I will explain, step by step, how to build a crowd detection pipeline entirely based on image processing methods. The pipeline consists of 2 components. The first component concerns crowd classification and the second one concerns crowd localization. I will develop in the following sub-sections each component in detail.

### 2.1 Crowd classification
In this project, the crowd classification problem is resolved using fractal dimension. But before proceeding with classification  problem, I would like to present the fractal dimension contecpt. 

#### 2.1.1 Fractal dimension
A. Backes  et al. explains the concept of fractal dimension as: "A measure of how fast the length of a curve increases as the size of the measuring stick is shortened" [1]. And Robert L. Devaney defines the fractal dimension as: "A measure of how complicated a self-similar figure is" [2]. 

There are several ways to compute the fractal dimension. I have chosen the box bounting method, aka Minkowski-Bouligand Dimension. The fractal dimension (FD) is given by:

<p align="center">
$$ FD = \lim_{r\to 0} \frac{log(N(r))}{log(\frac{1}{r})} $$ (1)
</p>

Where $$N$$ is the number of required boxes to cover the fractal and $$r$$ is the boxes side. The choice of the boxes side parameter is crucial. In fact, when $$r$$ is too small, the fracal dimension becomes very accurate. However, if $$r$$ becomes too big, the fractal may not be correctly covered by the boxes and this surely yields to imprecise results. 


In practise, fractal dimension is widely employed to measure and estimate costline mapping. If the goal is to compare which among Australia and Great Britain has the biggest coastline, it would be enough to compute the FD of each map and the one having the biggest FD will be considered as the map with the biggest coastline.

#### 2.1.1 Fractal dimension-based model for classification
Drawing on the previous  coastline estimation example, now let's see how fractal dimension can help with crowd classification. 

Crowd classification consists of analyzing an image and saying whether it contains a crowd or not. In this project, a crowd is considered as a grouping of at least 5 persons. If a crowd is correctly extracted from an image with its irregular contours, the fractal dimension of these contours can be computed. 

Imagine a scene with only 4 persons. Relying on box counting method, the 4 persons should be coverd by a sufficient number of boxes in order to get a precise fractal dimension. If more than 4 persons are present in the scene, the computed fractal dimension naturally increases. Assuming this, the crowd classification problem is represented by a thresold filtering on the computed fractal dimension. Let $$t_{FD}$$ be the threshold on the crowd fractal dimension, the classification is built as follows : 

$$
y = \left\{
    \begin{array}{ll}
        crowd & \mbox{if } FD >= t_{FD} \\
        no crowd & \mbox{otherwise}
    \end{array}
\right.
$$

#### 2.1.1 Crowd classification pipeline

 As shown in the figure Fig. 3, 


The figure Fig. 3 illustrates the general crowd detection pipeline.

<p align="center">
  <img width="754" height="140" src="/assets/images/crowd_detection/crowd_detection_pipeline_classif.png">
  <br>
  Figure 3: Crowd classification pipeline.
</p>


<p align="center">
  <img width="754" height="140" src="/assets/images/crowd_detection/crowd_detection_pipeline_locali.png">
  <br>
  Figure 4: Crowd localization pipeline.
</p>


 The components share some pre-pocessesing methods. which is based on fractal dimension and local density. 
### Crowd classification 
In order to perform crowd classification, I have built my classification on fractal dimension.
### Crowd localization
### System Pipeline

## Model implementation
### Requirements

## Model training
### Datasets
### Data pre-processing
### Training Setup


## Evaluation
## Running the Application
To test the model, you click on this link to load the Violence Detection Web App.

## Further Steps

## Conclusion
The proposed model is still far from saturating the benchmark metrics. If complicated backgrounds are crossed, the model may miss  targets or may provide an imprecise bounding box. However, the model is only based on image processing methods for the task of crowd detection. In addition, no intelligence is behind the established process. 


You can access the complete code via the [GitHub repository](https://github.com/AsmaBRZ/Crowd-detection).

## References
[1] A. Backes and O. Bruno. Fractal and multi-scale fractal dimension analysis : a comparative study of bouligand-minkowski method.ArXiv, abs/1201.3153, 2012.

[2] Robert L. Devaney. Fractal dimension. http ://math.bu.edu/DYSYS/chaos-game/node6.html,1995.

[3] Nilam Sjarif, Siti Mariyam Shamsuddin, Siti Mohd Hashim, and Siti Yuhaniz. Crowd analysis and its applications. volume 179, pages 687–697, 01 2011.