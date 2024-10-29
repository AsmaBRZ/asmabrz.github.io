---
layout: splash
header:
  overlay_image: /assets/images/robot.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background

feature_row:
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
