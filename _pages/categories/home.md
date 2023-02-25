---
title: "Home"
permalink: /home/
layout: category
author_profile: true
paginate: 5 # amount of posts to show
paginate_path: /page:num/
toc: true
toc_sticky: true
---

<!-- 
  category를 생성했을 때 추가해야할 것들
  1. assign sum카테고리명 = site.categories.카테고리명 | size 
  2. Projects처럼 큰 카테고리는 따로 만들거나 Blog 안에 들어가는 작은 카테고리 같은 경우는 <ul>, <li>로 적절히 집어 넣을 것
  2-1. Blog 안에 들어가는 작은 카테고리 같은 경우 " | plus: sum카테고리명"를 추가하여 합계에 누적시키기
  3. Blank CR로 모양 잘 맞추기
  
  Referance
  포스트 수: https://ansohxxn.github.io/blog/category/#%EC%A0%84%EC%B2%B4-%EA%B8%80-%EC%88%98
  Liquid문법 응용: https://shopify.github.io/liquid/ 
-->

{% assign sum = site.posts | size %}

{% assign sumProjects = site.categories.projects | size %}

{% assign sumBlogOnly = site.categories.blog | size %}
{% assign sumEmbedded = site.categories.embedded | size %}
{% assign sumCircuit = site.categories.circuit | size %}
{% assign sumProgramming = site.categories.programming | size %}
{% assign sumOtherthings = site.categories.otherthings | size %}
{% assign sumGithubpages = site.categories.githubpages | size %}

{% assign sumEtc = site.categories.etc | size %}

Total number of posts: {{sum}}
{: .notice--info}

<html> <!--Projects-->
  <head>
    <a href="/projects/" style="color:#229756; font: bold 1.3em GyeonggiTitleM; ">Projects ({{sumProjects}})</a>
  </head>
</html>

<html> <!--Blank CR-->
  <head>
    <br><br>  
  </head>
</html>

<html> <!--Blog-->
  <head>
    <a href="/blog/" style="color:#229756; font: bold 1.3em GyeonggiTitleM">Blog ({{ sumBlogOnly | plus: sumEmbedded | plus: sumCircuit | plus: sumProgramming | plus: sumOtherthings | plus: sumGithubpages }})</a>
  </head>
  <body> 
    <ul>
      <li><a href="/embedded/" style="color:gray">Embedded ({{sumEmbedded}})</a></li>
      <li><a href="/circuit/" style="color:gray">Circuit ({{sumCircuit}})</a></li>
      <li><a href="/programming/" style="color:gray">Programming ({{sumProgramming}})</a></li>
      <li><a href="/otherthings/" style="color:gray">Other Things ({{sumOtherthings | plus: sumGithubpages}})</a></li>
      <ul>
        <li><a href="/githubpages/" style="color:gray">GitHub Pages ({{sumGithubpages}})</a></li>
      </ul>
    </ul>
  </body>
</html> <!--Auto Blank  CR Because of <ul>-->

<html> <!--etc.-->
  <head>
    <a href="/etc/" style="color:#229756; font: bold 1.3em GyeonggiTitleM">etc. ({{sumEtc}})</a><br>
  </head>
</html>