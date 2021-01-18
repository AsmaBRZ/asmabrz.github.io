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


According to Google Scholar, 1460 papers have been published concerning crowd detection ot this day. There are a myriad of areas where crowd detection intervenes. The figure Fig. 2 shows some of these areas.




<p align="center">
  <img width="754" height="140" src="/assets/images/crowd_detection/crowd_detection_app.png">
  <br>
  Figure 2:  Application of crowd detection in different areas.
</p>

## Model architecture
### Crowd classification
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
[1] Nilam Sjarif, Siti Mariyam Shamsuddin, Siti Mohd Hashim, and Siti Yuhaniz. Crowd analysisand its applications. volume 179, pages 687–697, 01 2011.