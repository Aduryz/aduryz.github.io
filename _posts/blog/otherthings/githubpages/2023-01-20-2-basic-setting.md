---
title: \[GitHub Pages 블로그\] 기본 설정
excerpt: _config.yml에서의 기본 설정

categories:
  - githubpages
tag:
  - blog
toc: true
toc_sticky: true

date: 2023-01-20T11:57:09.660Z
last_modified_at: 2023-01-25T13:18:24.961Z
---

{{ page.excerpt }}
{: .notice--info}
대부분의 Jekyll theme에서는 최상위 폴더에 존재하는 기본 설정 파일인 `_config.yml`로 기본 설정이 가능하다. 여기서는 **Minimal Mistakes** 기준으로 설명한다.
여기서 다루지 않는 설정들은 내가 모르거나 추후 다룰 것.
{: .notice--info}

[Minimal Mistakes 기본 가이드](https://mmistakes.github.io/minimal-mistakes/docs/configuration/)에서 official한 설정 변경 방법을 볼 수 있다.

# skin
```yml
minimal_mistakes_skin : "default"  # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
```
여기서 기본적으로 제공되는 skin으로 변경하거나 내가 만든 skin으로 변경이 가능하다.

# Site Settings
기본적인 사이트 설정
{: .notice--info}

```yml
# Site Settings
locale : "en-US" # 기본적인 UI의 언어
title : "Arduriz.log" # 블로그의 이름을 설정 (블로그의 왼쪽 상단과 브라우저 주소창에 표시됨)
title_separator : "-" # 브라우저의 주소창에서 title을 구분하는 마크
subtitle : # "배우고 경험한 것을 적는 블로그" # 블로그의 왼쪽 상단에 표시되는 subtitle
name : "Arduriz" # 사이트 이름
description : "배우고 경험한 것을 적는 블로그" # 블로그 설명
url : "https://arduriz.github.io" # 블로그 주소
baseurl : # the subpath of your site, e.g. "/blog" # 서브 경로가 있는 경우 기재
repository : "arduriz/arduriz.github.io" # repo 이름
teaser : # path of fallback teaser image, e.g. "/assets/images/500x300.png" # teaser 이미지
logo : # "/assets/images/blog/logo.png" # logo 이미지, 최상단 메뉴 바에 보이게 됨
masthead_title : "Arduriz.log" 
# breadcrumbs : false # true, false (default) # 자동으로 화면 크기에 맞게 UI 크기가 조정되는 기능인데 beta인듯
words_per_minute : 200 # 글을 읽는데 걸리는 시간의 기준이 되는 글자수
```

* `name`이랑 `description`은 사이트 설명으로 SEO와 관계된 정보이다.

* `url`에서 설정된 url 정보는 markdown 본문에서 블로그 사이트 주소를 지정하는 변수로 사용된다.
예를 들어 아래와 같이 markdown에서 기재하면
	```
	<{{ site.url }}{{ site.baseurl }}/blog/start-blog/>
	```
	`_config.yml` 파일에 기재된 site.url 정보를 기반으로 링크 주소를 구성해준다. 

# 오픈그래프 이미지 등록
```yml
og_image : "/assets/images/blog/logo.png"
```
오픈그래프 프로토콜은 SNS 등에서 어떤 링크에 대한 미리보기 제목, 설명, 이미지를 구성할때 메타 데이터 표기 방법이다.
og_image 그림 파일을 등록하면 블로그 글이 링크될때 기본으로 적용될 이미지를 지정한다. 

# Author
왼쪽에 보여지는 Author의 정보
{: .notice--info}

```yml
# Site Author
author:
	name : "CHOI Hyunseo" # 이름
	avatar : "/assets/images/blog/logo.png" # logo
	bio : "**재능은 배움을 통해 얻어진다**는 가치관을 <br> 가지고 **임베디드**, **회로**, **프로그래밍**을 <br> 배우고 경험하는 중인 전자공학도입니다." # 설명, Markdown 문법 적용가능
	# bio 아래에 보여지는 지역, sns 정보들
	location : "Incheon, Korea"
	email : # chs902m@gmail.com
	links:
		- label: "Facebook"
		icon: "fab fa-fw fa-facebook-square"
		# url: "https://facebook.com/"
		- label: "About"
		icon: "fas fa-fw fa-user"
		url: "https://github.com/Arduriz"
		- label: "Email"
		icon: "fas fa-fw fa-regular fa-envelope"
		url: "mailto:chs902m@gmail.com"
		- label: "GitHub"
		icon: "fab fa-fw fa-github"
		url: "https://github.com/Arduriz"
		- label: "Instagram"
		icon: "fab fa-fw fa-brands fa-instagram"
		url: "https://instagram.com/choi.sunshining/"
```
- url을 주석처리하면 그 sns는 안 보이게 됨
- fas icon 다른 것들도 적용가능, 사이트에 들어가서 가져오면 됨

![그림9](/assets/images/post/blog-otherthings-githubpages/1-9.png) <br>
이렇게 보임

# 블로그 첫 페이지
```yml
# Outputting
permalink: /:categories/:title/
paginate: 5 # 첫 페이지에 보여줄 최근 게시물 수를 지정
paginate_path: /page:num/
timezone: Asia/Seoul
```
- paginate는 첫페이지에서 보여주는 recent posts의 개수이다. 이 개수를 넘어서는 오래된 게시물들은 다름 페이지 번호로 넘어간다.
- timezone은 한국이면 Seoul을 사용한다.

# post 기본 설정
```yml
# Defaults
defaults:
	# _posts
	- scope:
		path: ""
		type: posts
	  values:
		layout: single
		author_profile: true
		show_date: true  # 이걸 추가하면 작성 일자도 보이게 할 수 있음
		read_time: true
		comments: # true # 댓글 기능
		share: true
		related: true
```

# 기타
```yml
atom_feed: # RSS hide
	hide: true
	
date_format: "%Y. %m. %d"
```

# Reference
> [Minimal Mistakes 기본 가이드](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) <br>
> [하우투: GitHub Pages 블로그 따라하기](https://devinlife.com/howto/) <br>
> [따라쟁이의 인공지능 블로그](https://khw11044.github.io/githubpages/) <br>

이 포스트에선 참고하지 않았지만 다른 기능을 추가할 때 참고한 포스트
> [https://ansohxxn.github.io/categories/blog](https://ansohxxn.github.io/categories/blog) <br>
> [https://etch-cure.github.io/categories/#blog](https://etch-cure.github.io/categories/#blog) <br>
> [https://eona1301.github.io/a_to_z/GithubBlog/#00-github-blog-a-to-z](https://eona1301.github.io/a_to_z/GithubBlog/#00-github-blog-a-to-z) <br>
> [https://github.com/choiiis/minimal-mistakes-choiiis-customized](https://github.com/choiiis/minimal-mistakes-choiiis-customized) <br>
> [https://danggai.github.io/categories/#github-io](https://danggai.github.io/categories/#github-io) <br>
