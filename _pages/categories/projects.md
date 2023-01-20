---
title: "Projects"
permalink: /projects/
layout: category
author_profile: true
toc: true
toc_sticky: true
---


**Projects** & **Toy Projects** that have gone ahead @ universities, etc.

{% assign posts = site.categories.projects %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
