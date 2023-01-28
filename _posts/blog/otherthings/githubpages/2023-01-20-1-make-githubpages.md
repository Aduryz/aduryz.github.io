---
title: GitHub Pages 블로그 - 생성
excerpt: GitHub Pages와 Jekyll을 이용한 블로그 생성

categories:
  - githubpages
tag:
  - blog
toc: true
toc_sticky: true

date: 2023-01-20T11:56:09.660Z
last_modified_at: 2023-01-25T13:18:24.961Z
---

{{ page.excerpt }}
{: .notice--info}
GitHub Pages와 Jekyll로 일반적인 사이트도 만들 수 있지만 나는 일단 블로그에 중점을 두고 설명한다.
{: .notice--info}

# Editor (개발환경 프로그램)
*나는 GitHub Pages를 `Visual Studio Code`를 이용하여 제작하였으나 다른 editor로 제작하여도 될 듯하다.*

#  Theme
나는 Jekyll을 사용하기로 했다. 내가 본 테마들은 [내가 고려한 Jekyll themes](https://arduriz.github.io/githubpages/jekyll-theme/) 포스트를 참고하길 바란다. 나는 **Minimal Mistakes**를 선택하였다.
내가 본 테마 말고도 다른 테마를 참고하고 싶다면 [http://themes.jekyllrc.org/](http://themes.jekyllrc.org/) 이 사이트를 추천한다. 정렬 기능이 있어서 고르기가 좋다.

마음의 드는 테마를 선택했다면 해당 테마 페이지에 있는 파일(zip) 다운로드 또는 `clone`을 하여 파일들을 다운 받자. *나는 zip파일을 다운해서 압축을 풀고 진행했다.*

# Git, Jekyll, Ruby설치
GitHub Pages와 Jekyll을 이용하여 블로그를 생성하므로 이 둘의 설치는 필수적이다. Ruby는 Jekyll의 기반이 되는 언어라 역시 설치가 필요하다. *(Ruby를 잘 알지 못해도 블로그 생성에는 전혀 어려움이 없다.)*
Git은 [Git 설치 가이드](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-Git-%EC%84%A4%EC%B9%98)를 참고하여 설치하면 된다.

[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)에서 Ruby를 다운받는다.
![그림1](/assets/images/post/blog-otherthings-githubpages/1-1.png) <br>
=> 표시가 되어 있는 버전의 Installer를 다운 후 설치를 진행한다. 별도 설정없이 Next만 누르면 잘 설치된다.

![그림2](/assets/images/post/blog-otherthings-githubpages/1-2.jpeg) <br>
이 때 체크박스는 모두 체크해준다.

![그림3](/assets/images/post/blog-otherthings-githubpages/1-3.png) <br>
이 때 1을 누르고 CR(Carriage Return, 엔터키 누름)한다.

![그림4](/assets/images/post/blog-otherthings-githubpages/1-4.png) <br>
쭉 설치가 되고 마지막에 CR하면 터미널이 꺼진다.

![그림5](/assets/images/post/blog-otherthings-githubpages/1-5.png) <br>
cmd를 열고 ruby –v 명령어를 입력하여​ 루비가 잘 설치되었는지 확인해 본다.

테마가 들어있는 폴더에서 우클릭을 한 후 `visual studio code`를 연다. *(우클릭을 했는데 `Code로 열기`가 보이지 않는다면 아래 이미지의 박스를 체크하면서 다시 설치하면 된다.)*
![그림6](/assets/images/post/blog-otherthings-githubpages/1-6.png) <br>

`visual studio code`에서 <code>Ctrl+`</code>로 Terminal을 연다.

`chcp 65001`를 실행한다. 인코딩을 부여하기 위한 명령어인데 실행하지 않을 경우 이후 진행하게 될 온갖 명령어에서 오류가 발생하므로 꼭 진행하여야 한다.

이제 Ruby에서 지원하는 gem 명령어를 통해 Jekyll은 물론 종속된 필요한 라이브러리를 설치하자. 참고로, gem이란 루비에서 제공하는 라이브러리를 편리하게 설치할 수 있도록 지원되는 도구이다.
`gem install bundler jekyll minima jekyll-feed tzinfo-data rdiscount`

완료되면 아래 코드를 차례로 입력한다.
```
bundle update --bundler
```
```
bundle install
```
```
bundle exec jekyll serve
```
<br>

![그림7](/assets/images/post/blog-otherthings-githubpages/1-7.jpeg) <br>
위와 같은 문구가 나오면 `Ctrl+C`, `Y`, `Y`로 종료하고 `gem ‘wdm’, ‘>= 0.1.0’`을  Gemfile의 가장 아래에 붙여 넣고 저장을 해준 후 다시 `bundle exec jekyll serve`를 실행하면 위의 문구가 사라진다.
[http://127.0.0.1:4000/](http://127.0.0.1:4000/)를 브라우저에서 실행시키면 Jekyll이나 테마에서 제공한 기본 블로그 화면이 나오게 된다. *(127.0.0.1 주소는 컴퓨터 네트워크에서 본인 컴퓨터의 주소를 의미한다. 그래서 위의 접속 주소로 접속을 시도하면 테스트 컴퓨터(Jekyll을 구동하고 있는 컴퓨터)에서만 접속이 가능하다. Jekyll을 실행 시킬 때 아래처럼 호스트 주소(테스트 컴퓨터의 ip 주소)를 기재할 수 있다. 이렇게 하면 다른 디바이스의 브라우저로 테스트 컴퓨터 웹페이지 [http://192.168.0.8:4000/](http://192.168.0.8:4000/)를 접속할 수 있다.)*

# GitHub Repository 생성
*username*.github.io로 repo를 생성한다. *username*.github.io/*sth*으로 생성하면 또 다른 링크의 블로그도 만들 수 있다. *(나는 about을 이렇게 블로그를 하나 더 만드는 방식으로 다른 테마를 적용하여 제작하였다.)*

그리고 이 repo에 `commit`하면 자동으로 [https://*username*.github.io](https://username.github.io)주소로 웹호스팅을 해준다. *(나는 GitHub Desktop으로 `commit`했다.)*

![그림8](/assets/images/post/blog-otherthings-githubpages/1-8.png) <br>
`action`에서 이렇게 모두 완료되어야 저 주소에서 블로그가 보인다.

이렇게 하면 GitHub Pages 블로그가 생성된다.

# 블로그 수정
앞으로 블로그를 수정할 때는 다음 2가지를 이용하여 수정할 수 있다.

## bundle exec jekyll serve
`visual studio code`에서 파일들을 수정한 후 저장한 뒤에 `bundle exec jekyll serve`를 실행하면 [http://127.0.0.1:4000/](http://127.0.0.1:4000/)에서 수정사항이 반영된 블로그가 보여지게 된다.
**이 방식으로 빠르게 수정사항을 확인 할 수 있다.**

여기서 주의 사항은 `_config.yml` 파일 만큼은 Jekyll service를 중단하고 다시 사이트 빌드가 필요하다. `_config.yml` 파일 안에는 여러 환경설정과 변수들이 저장되어 있는데 사이트가 빌드 될 때 한번만 읽어들이기 때문이다.
{: .notice--danger}

## GitHub Pages
`bundle exec jekyll serve`로 수정사항을 확인 후 만족스럽다면 repo에 `commit`해서 실제 블로그에 적용을 할 수 있다.