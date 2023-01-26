---
title: "Other Things"
permalink: /otherthings/
layout: category
author_profile: true
toc: true
toc_sticky: true
---


**git/github**, **jekyll**, etc.

<span style="
font-family: 'GyeonggiTitleM';
font-size: 1.3em;
">
[GitHub Pages]
</span>

[GitHub Pages]: /githubpages/

## All posts

{% assign posts = site.categories.otherthings %}
{% assign posts = site.categories.githubpages %}

{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
