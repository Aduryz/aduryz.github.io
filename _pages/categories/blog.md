---
title: "Blog"
permalink: /blog/
layout: category
author_profile: true
toc: true
toc_sticky: true
---


**Things studying** or **Things want to share**

<span style="
font-family: 'GyeonggiTitleM';
font-size: 1.3em;
">
[Embedded]
</span> <br>
<span style="
font-family: 'GyeonggiTitleM';
font-size: 1.3em;
">
[Circuit]
</span> <br>
<span style="
font-family: 'GyeonggiTitleM';
font-size: 1.3em;
">
[Programming]
</span> <br>
<span style="
font-family: 'GyeonggiTitleM';
font-size: 1.3em;
">
[Other Things]
</span> <br>
  
[Embedded]: /embedded/
[Circuit]: /circuit/
[Programming]: /programming/
[Other Things]: /otherthings/

## All posts

{% assign posts = site.categories.blog %}
{% assign posts = site.categories.embedded %}
{% assign posts = site.categories.circuit %}
{% assign posts = site.categories.programming %}
{% assign posts = site.categories.otherthings %}

{% assign posts = site.categories.githubpages %}

{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
