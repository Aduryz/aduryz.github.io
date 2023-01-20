---
title: "Other Things"
permalink: /otherthings/
layout: category
author_profile: true
toc: true
toc_sticky: true
---


**git/github**, **jekyll**, etc.

{% assign posts = site.categories.otherthings %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
