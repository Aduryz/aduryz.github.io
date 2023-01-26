---
title: ※ 왜 GitHub Pages와 Jekyll을 선택하였는가
excerpt: 다른 플랫폼 대신 GitHub Pages와 jekyll을 선택한 이유

categories:
  - githubpages
tag:
  - blog
toc: true
toc_sticky: true

date: 2023-01-20T11:53:09.660Z
last_modified_at: 2023-01-20T11:56:09.660Z
---

{{ page.excerpt }}
{: .notice--info}

# Blog Platform
크게 고려한 것은 **GitHub Pages**, **velog**이다. <br>
네이버 블로그, 티스토리 같은 일반적인 서비스형 블로그는 프로그래밍 소스 코드를 많이 적기에는 개발자 친화적이지 않다고 생각하여 배재했다.

**velog**는 디자인이 마음에 들고 개발자가 만들어서 아주 매력적으로 다가왔다. 하지만 잠깐 사용해보니 내가 원하는대로 customizing을 할 수 없어서 일일히 마크다운과 html문법으로 post마다 customizing해야하는 것이 불편하였다.

그래서 최종적으로 내마음대로 customizing하기 위해 **GitHub Pages**를 선택하게 되었다.그리고 어차피 소스 코드를 github에 업로드하기 때문에 git에 익숙해질 겸 일석이조라고 생각하게 되었다.

# Static Websites Generator
크게 **Jekyll**과 **Hugo** 중에 고민했다.

**Jekyll**의 경우에는 다른 곳에서는 쓸 일이 없고 앞으로 내가 배우지도 않을 언어인 Ruby기반인 점이 단점으로 다가왔다. 그래서 범용성이 넓고 앞으로 내가 배울 흥미가 있는 go를 기반으로 한 **Hugo**를 이용하여 제작하려고 했다.

하지만 **Hugo**를 이용하여 제작하다보니 자료가 별로 없어 처음 제작하기에는 진입장벽이 높았다. 그래서 일단 처음 만드는 것이므로 자료가 많은 **Jekyll**을 이용하여 만들기로 하였다.

**Jekyll**의 속도가 만족스럽지 못해서 속도에서 강점을 가지는 **Hugo**로 추후 옮기게 될 수도 있다.

> ## Jekyll
Jekyll은 루비로 만든 정적 웹사이트 생성기(static websites generator)이다. (만약, 루비를 모른다면 그냥 컴퓨터 언어의 한 종류라는 것만 인식하고 넘어가자.) Jekyll은 Template과 Contents를 등의 다양한 포맷의 텍스트 데이터를 읽어서 static websites를 생성해준다. 이를 알아듣기 쉽게 설명하면 markdown 파일을 사용하는 블로그 플랫폼이다. <br/><br/>
웹사이트를 운영하기 위한 html 관련 지식들을 알 필요가 없이, markdown 파일로 간단히 문서를 작성하면 html 파일로 이를 변환해주는 작업을 해주며 변환 결과물을 토대로 웹사이트를 구축해서 서비스해준다. markdown 파일을 포함한 블로그 컨텐츠들을 html 파일로 변환해주는 역할을 하기때문에 static websites generator라고 한다. 위 그림에서 블로그 컨텐츠들이 Jekyll을 통해서 html(static websites)로 변환되는 관계를 확인할 수 있다. markdown 파일 형식은 텍스트 파일 포맷 중의 한 종류인데 배우기가 매우 쉬우므로 makrdown을 모른다고 GitHub Pages를 사용하지 못할꺼라는 생각은 하지말자. <br/><br/>
정적 웹사이트(static websites)의 대한 정의만 살펴보자. 정적 웹사이트는 어떤 웹사이트 주소를 접속한다면 모든 사람들이 모든 결과물(html)이 동일하면 정적인 웹사이트이다. 이미 html 페이지가 구성이 되어있어서 사람들이 해당 주소에 접속했을때 보여주는 결과물이 하나 뿐인 웹사이트인다. 반대로 동적으로 구성된 웹사이트들은 동일 웹사이트에 접속을 해도 사용자의 의한 요청에 따라 보여지는 웹페이지가 각기 다른 경우가 있다. 이런 경우 보통 웹어플리케이션 서버를 운영하고 사용자 요청에 따른 웹페이지 결과를 구성해서 보여주는 형태이다.

> ## GitHub Pages
GitHub Pages는 GitHub에서 제공하는 정적 웹사이트(static websites) 호스팅 서비스이고, 많은 사람들이 이를 이용하여 블로그를 게시하고 있어서 블로그 서비스라고 인식되고 있다. 많은 개발자들이 GitHub를 사용하여 git로 코드를 업로드하고 공유한다. GitHub에서는 git 서비스 뿐만 아니라 쉽게 정보를 게시할 수 있도록 블로그 서비스도 제공하고 있는 것이다. <br/><br/>
Jekyll을 이용하면 GitHub를 사용하지 않고도 로컬 컴퓨터에서 블로그 웹호스팅이 가능하다. 단지, 로컬 컴퓨터에서 웹호스팅을 할 경우에는 24시간 컴퓨터를 켜두어야 하고 웹서비스가 에러는 없는지 모니터링 해야 하는 등 관리 작업이 필요하다. 일반인들이 이러한 관리를 수행하기는 힘들기 때문에 로컬 컴퓨터를 통한 웹호스팅 보다는 GitHub Pages를 이용하는 것이다. <br/><br/>
GitHub Pages에도 내부에 Jekyll이 설치되어 있다. 블로거들이 markdown 파일로 글을 작성하여 git push로 업로드하면, GitHub Pages 내부에서 Jekyll이 이를 인식한 후 html로 변환한 후 웹호스팅을 하는 것이다. <br/><br/>
GitHub Pages를 사용하면 로컬 컴퓨터에 Jekyll을 설치하지 않아도 된다고 해두고 Jekyll을 설치하는 이유는 무엇일까? <br/><br/>
실제로 글을 하나 써보면 몇번씩 오탈자를 발견하게 되고 글을 구성도 다시 바꾸게 되는 일이 빈번하게 일어난다. 그런데 로컬 컴퓨터에서 확인없이 GitHub Pages에서만 진행하게 된다면, git 업로드 후에 GitHub Page에서 업데이트 내용이 반영되기를 기다리고 확인하고 다시 수정하고…하는 작업 시간이 오래 걸리게 된다. <br/><br/>
결론이다. GitHub Pages에서의 블로깅 과정은 보통 이렇다. markdown으로 포스팅 할 글을 작성한다. 그리고 Jekyll이 설치된 로컬 컴퓨터에서 html을 변환을 수행하여 게시할 글의 내용을 확인하다. 이 때, 오탈자 및 오류 등을 살피고 수정한다. 다시 로컬 생성된 웹사이트에서 내용을 학인하고 오류가 있으면 재수정한다. 이 과정을 반복하고 게시가 결정되면 git repo로 작업 결과물을 push한다. git push가 이뤄지면 GitHub Pages가 이를 자동으로 인식하여 웹사이트를 업데이트한다. 최종적으로 GitHub Pages의 블로그 내용을 점검한다.

> ## Jekyll 과 GitHub Pages를 사용한 블로깅 장점
Jekyll을 사용하는 블로깅의 장점은 makrdown 파일 포맷과 git 를 사용한다는 점이다. <br/><br/>
markdown 형식은 html 보다 간단하고 이해하기 쉽다. html에 직접 블로그를 작성하는 것보다 markdown으로 글을 쓰는 것이 더 간편하다는 의미이다. markdown은 간단하기 때문에 배우기도 쉽다. markdown 포맷에 대한 지식이 없어도 배우는데 1시간이 채 걸리지 않는다. 보통 블로그 플랫폼에서 제공하는 에디터보다 markdown 작성이 더 쉽다. <br/><br/>
그리고, GitHub Pages를 통하면, git통해서 블로그를 관리하고 글을 포스트할 수 있다. git는 익숙치 않다면 좀 공부가 필요할 것이다. 하지만 익숙해지면 블로그 히스토리 관리나 글 작성에 있어서 매우 편하다는 것을 느낄 수 있다. <br/><br/>
GitHub에 매우 다양한 무료 테마(theme)들이 오픈 소스로 공개되어 있다는 점도 큰 장점이다. 물론 유료 버전들도 있고 이런 유료 버전들이 더 완성도가 높은 것도 사실이지만 훌륭한 무료 버전들도 많이 있다. 이런 테마를 다운로드하여 본인의 설정(Customizing)으로 변경하는 것도 가능하다.

Reference: [하우투: GitHub Pages 블로그 따라하기](https://devinlife.com/howto/)
{: .small}
