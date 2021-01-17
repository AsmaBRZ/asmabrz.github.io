---
layout: splash
header:
  overlay_image: /assets/images/robot.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background

feature_row:
  - image_path: /assets/images/teasers/image_classif.png
    alt: "2016 election map and cartogram"
    title: "Image classification"
    excerpt: "Classification of images containing dog, cat, truck...etc."
    url: "https://image-classif.herokuapp.com/"
    btn_label: "Open"
    btn_class: "btn--primary"
  - image_path: /assets/images/teasers/cells-seg.png
    alt: "2016 election map and cartogram"
    title: "Cells segmentation"
    excerpt: "Segmentation of biomedical images using UNet++"
    url: "https://image-classif.herokuapp.com/"
    btn_label: "Open"
    btn_class: "btn--primary"
  - image_path: assets/images/teasers/mask-detection.png
    alt: "Rectangular aggregations at the LHC"
    title: "Mask detection COVID-19"
    excerpt: "Detection of persons correclty wearing, not wearing and wrongly wearing masks."
    url: "https://image-classif.herokuapp.com/"
    btn_label: "Open"
    btn_class: "btn--primary"

---


<h1> Recent Posts </h1>
<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      - <small><strong>{{ post.date | date: "%B %e, %Y" }}</strong></small>.
    </li>
  {% endfor %}
</ul>

See all posts [here](/archive/).


<h1> Projects </h1>

{% include feature_row id="feature_row" %}


{% comment %}
This is a comment: it will not show up on the website :)
{% endcomment %}
