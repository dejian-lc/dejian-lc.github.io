---
layout: about
title: about
permalink: /
subtitle: PhD Student, National University of Defense Technology (国防科技大学)
motto: "I will keep moving forward, until fate is crushed underfoot."

profile:
  align: right
  image: "lc-profile.png"
  image_circular: false # crops the image to make it circular
  more_info: >
    <p><i class="fa-solid fa-graduation-cap"></i> PhD Student</p>
    <p><i class="fa-solid fa-building-columns"></i> National University of Defense Technology</p>
    <p><i class="fa-solid fa-location-dot"></i> Changsha, China</p>
    <p><i class="fa-solid fa-envelope"></i> liudawn@nudt.edu.cn</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

My research interests include generative detection, multimodal models, AIGC, and world models.

<h2 class="section-title">Education</h2>
<div class="section-block about-education">
  {% include cv/education.liquid entries=site.data.cv.cv.sections.Education %}
</div>
