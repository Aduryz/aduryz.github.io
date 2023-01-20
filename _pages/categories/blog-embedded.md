---
title: "Embedded"
permalink: /embedded/
layout: category
author_profile: true
toc: true
toc_sticky: true
---


**Arduino**, **Rasberry Pi**, **Assembly**, etc.

{% assign posts = site.categories.embedded %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
