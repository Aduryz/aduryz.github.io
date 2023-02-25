---  
title: ※ About GitHub Pages 제작
excerpt: 블로그와 별개로  About GitHub Pages 제작한 과정

categories:
  - githubpages
tag:
  - blog

date: 2023-02-25T06:29:08.877Z
last_modified_at: 2023-02-25T06:29:08.877Z 
---  
  
{{ page.excerpt }}  
{: .notice}

# Theme
[※ 내가 고려한 Jekyll themes](https://arduriz.github.io/githubpages/jekyll-theme/)에서 [Neumorphism](https://github.com/longpdo/neumorphism)를 선택하였다.

# Clone
## Prerequisites
이 테마에 필요한 Prerequisites를 미리 설치해놓아야 한다.
### NodeJS
[NodeJS](https://nodejs.org/en/)에서 LTS를 설치한다.

### Jekyll
[GitHub Pages 블로그 - 생성](https://arduriz.github.io/githubpages/1-make-githubpages/)에 나온 방식으로 Jekyll을 설치한다.

### Yarn
vs code에서 다음 명령어를 터미널에서 실행하여 설치한다.
```
npm install -g yarn
```

## Clone
[Neumorphism](https://github.com/longpdo/neumorphism)에서 `Use this template`으로 `clone`한다.

그리고 `clone`한 폴더에서 vs code를 열고 터미널에서 다음 명령어를 실행한다.

```
yarn
bundle install
```

# GitHub Pages 하나 더 제작
나는 지금 GitHub Pages가 이미 하나가 있는데 하나 더 만들고 싶은 것이다.
{: .notice--warning}

`clone`한 `repo`의 이름은 마음대로 정해도 된다. *(난 `about`으로 했다.)*

`clone`한 `repo`의 `Settings`-`Pages`로 간다.

![깃허브페이지로 만드는 법](https://user-images.githubusercontent.com/65582244/221203014-73430cb7-05b8-4a85-b838-224c45379b59.png)
**빨간 네모**에서 `Branch`를 `None`에서 `Maste`r로 변경하고 `Save`한다. <br>
**노란 네모**처럼 조금 기다리면(`action`에서 과정 확인 가능) `repo`이름(`about`)을 뒤에 단 채로 생성된다.

## Build 실패
`action`에서 GitHub Pages `Build`를 실패할 수 있다.
{: .notice--warning}

해결방법은 `/_config.yml`에서 

```yml
plugins:
- "jekyll-github-metadata"
```
에서 주석처리하여
```yml
plugins:
# - "jekyll-github-metadata"
```
로 저장한다.

아니면 다음을 따른다.
<div  class="notice"  markdown="1"> 

### Github Metadata Plugin

If you want to automatically have your Github repositories pulled for the  _Open Source Projects_  section, then you also need to authenticate yourself for the Github Metadata plugin to work.

You need to generate a new personal access token on GitHub:

-   Go to the  [Github Token site](https://github.com/settings/tokens/new)
-   Select the scope `public_repository`, and add a description.
-   Confirm and save the settings. Copy the token you see on the page.
-   Create a `.env` file inside your repository and add your generated `JEKYLL_GITHUB_TOKEN`:

```
JEKYLL_GITHUB_TOKEN=0YOUR0GENERATED0TOKEN0
```

To complete the configuration for the Github Metadata plugin, you also need to change the value of `repository` inside `_config.yml`. After this, you should the Github Metadata plugin should work properly.
</div>

`css` 적용할 때 적용이 안 된다면 `github: [metadata]` 넣으면 적용된다. 단, **Github Metadata Plugin**을 완료해야한다.
{: .notice--success}


# bundle exec jekyll serve

[GitHub Pages 블로그 - 생성](https://arduriz.github.io/githubpages/1-make-githubpages/)을 참고하여 준비한 뒤 `bundle exec jekyll serve` 한 번 실행시켜보려고 하면 에러가 많이 난다.

## http://localhost:4000/about/

[http://127.0.0.1:4000/](http://127.0.0.1:4000/)로 접속하면 안된다. `username.github.io`가 아니라 새로운 `repo`이기 때문에 [http://localhost:4000/about/](http://localhost:4000/about/)로 접속해야 실행이 된다.
{: .notice--warning}

## 'require': cannot load such file -- webrick (LoadError)

`bundle add webrick`을 터미널에서 실행시켜 해결한다.
{: .notice--warning}

## plugins

```yml
plugins:
- "jekyll-github-metadata"
```
주석처리 한 plugin을 다시 활성화 시켜줘야한다.

일단 이렇게 하면 아마도 실행이 될 거다.
{: .notice--success}

---

# Personalize and Customize
## .yml 수정
### `/_config.yml`
주석보고 수정하면 된다. 특별히 어려운 건 없다.

`baseurl`을 유의해야한다. `"/about"`등으로 하자.
{: .notice--warning}

<div  class="notice"  markdown="1">
`/_config.yml`
```yml
github_username: arduriz
codepen_username: arduriz  #Homepage #landing-page.html에서 수정
dev_username: arduriz  #insta
linkedin_username:
twitter_username:
```
이 부분은 뒤에서 설명한다.
</div>

### `/_data`
주석을 참고하여 수정하면 된다.

## HTML수정 (@`/_includes`)

### `/_includes/landing-page.html`

<div  class="notice--success"  markdown="1">
![image](https://user-images.githubusercontent.com/65582244/221225201-a4b8c798-5042-4206-a344-f56d5fa6c6ba.png)<br>
얘네들을 수정해볼 것이다.
</div>

<div  class="notice"  markdown="1">
`/_config.yml`
```yml
github_username: arduriz
codepen_username: arduriz  #Homepage #landing-page.html에서 수정
dev_username: arduriz  #insta
linkedin_username:
twitter_username:
```
먼저 여기서 활성화시키고 싶은 만큼 닉네임을 적는다. `dev`처럼 내가 실제로 사용하는 소셜서비스가 아니어도 일단 아무거나 적어야 활성화가 된다.
</div>

<div  class="notice"  markdown="1">
`/_includes/landing-page.html`에서 수정을 원하는 서비스를 찾는다.
(아래 코드에선 `dev`)
```html
{% raw %}
      {% if site.dev_username != null %}
        <a class="social-link" aria-label="My DEV" target="_blank" rel="noreferrer"
          href="https://dev.to/{{site.dev_username}}"
        >
          <svg viewBox="0 0 200 200" class="circle">
            <circle cx="100" cy="100" r="80" />
          </svg>
          <div class="social">
            <svg class="social-svg" viewBox="0 0 48 48">
              <use x="12" y="12" width="24" height="24" viewBox="0 0 48 48" xlink:href="{{ "/assets/img/brands.svg#dev" | prepend: site.baseurl }}"></use>
            </svg>
          </div>
          <span class="label">DEV</span>
        </a>
      {% endif %}
{% endraw %}
```

이제부터 하나씩 수정할 것이다.

```html
        <a class="social-link" target="_blank" rel="noreferrer"
          href="https://www.instagram.com/choi.sunshining/"
        >
```

`aria-label`을 제거하고 `href=`에 내가 원하는 링크를 넣는다.

...


```html
<use  x="12"  y="12"  width="24"  height="24"  viewBox="0 0 48 48"  xlink:href="{{ "/assets/img/brands.svg#instagram"  |  prepend:  site.baseurl  }}"></use>
```

`/assets/img/brands.svg(파일)`에서 내가 원하는 서비스의 로고가 있는 지 보고 있으면 `/assets/img/brands.svg#(@코드)`에 원하는 서비스를 쓴다.

```html
<span  class="label">Instagram</span>
```

`label`에 원하는 라벨을 적는다.
</div>

서비스끼리 순서를 바꿔서 순서를 바꿀 수도 있다.
{: .notice--success}

</div>


### `/_includes/section-projects.html`

<div  class="notice"  markdown="1">
`/_includes/section-projects.html`
```html
  <p class="subtitle">
    Please refer to the Toy Project
    <a class="highlight-link" href="https://longpdo.github.io/" target="_blank" rel="noreferrer">
      here
    </a>.
  </p>
```

Toy Project 추가

...


```html
{% raw %}
        {% if project.demo %}
          <a class="highlight-link" href="{{project.demo}}" target="_blank" rel="noreferrer">
            view details
          </a>
        {% endif %}
{% endraw %}
```
`Demo` -> `view details`
</div>

### `/_includes/section-skills.html`

<div  class="notice"  markdown="1">
`/_includes/section-skills.html`
```html
<div id="skills">
  <input type="radio" id="all" name="filter" checked />
  <label class="filter-button neumorphism-button" for="all">All</label>
  <input type="radio" id="language" name="filter" />
  <label class="filter-button neumorphism-button" for="language">Languages</label>
  <input type="radio" id="tool" name="filter" />
  <label class="filter-button neumorphism-button" for="tool">HW tools</label>
  <input type="radio" id="framework" name="filter" />
  <label class="filter-button neumorphism-button" for="framework">SW tools</label>
```
SW tools, HW tools로 이름 바꿈, 순서바꿈
</div>

### `/_includes/section-timeline.html`

<div  class="notice"  markdown="1">
`/_includes/section-timeline.html`
```html
<p class="subtitle">
  For more information, have a look at my
  <a class="highlight-link" href="{{site.cv_download_link}}" target="_blank" rel="noreferrer">
    curriculum vitae
  </a>.
</p>
```
전부 주석처리

```html
<p  class="subtitle">
	Click on the title for more information on Education & Activity.
</p>
```
추가
</div>

### `/_includes/section-footer.html`

<div  class="notice"  markdown="1">
`/_includes/section-footer.html`
```html
{% raw %}
<div class="contact-icons">
  {% if site.codepen_username != null %}
  <a class="social-link black" target="_blank" rel="noreferrer"
    href="https://arduriz.github.io">
    <div class="social">
      <svg class="social-svg" viewBox="0 0 48 48">
        <use x="12" y="12" width="24" height="24" viewBox="0 0 48 48" xlink:href="{{ "/assets/img/brands.svg#readme" | prepend: site.baseurl }}"></use>
      </svg>
    </div>
  </a>
  {% endif %}

  {% if site.email != null %}
  <a class="social-link" aria-label="My E-Mail" href="mailto:{{site.email}}">
    <div class="social">
      <svg class="social-svg" viewBox="0 0 48 48">
        <use x="12" y="12" width="24" height="24" viewBox="0 0 48 48" xlink:href="{{ "/assets/img/solid.svg#envelope" | prepend: site.baseurl }}"></use>
      </svg>
    </div>
  </a>
  {% endif %}

  {% if site.github_username != null %}
  <a class="social-link" aria-label="My GitHub" target="_blank" rel="noreferrer"
    href="https://github.com/{{site.github_username}}">
    <div class="social">
      <svg class="social-svg" viewBox="0 0 48 48">
        <use x="12" y="12" width="24" height="24" viewBox="0 0 48 48" xlink:href="{{ "/assets/img/brands.svg#github" | prepend: site.baseurl }}"></use>
      </svg>
    </div>
  </a>
  {% endif %}

  {% if site.dev_username != null %}
  <a class="social-link black" target="_blank" rel="noreferrer"
    href="https://www.instagram.com/choi.sunshining/">
    <div class="social">
      <svg class="social-svg" viewBox="0 0 48 48">
        <use x="12" y="12" width="24" height="24" viewBox="0 0 48 48" xlink:href="{{ "/assets/img/brands.svg#instagram" | prepend: site.baseurl }}"></use>
      </svg>
    </div>
  </a>
  {% endif %}
{% endraw %}
</div>
```

소셜 서비스 추가

그 외 copyright 변경
</div>

### `/_includes/section-contact.html`

```html
<h1  class="title">{{site.contact_title}}</h1>
```
이 부분 빼고 다 날리고 Award & Experience를 `HTML`로 작성

## HTML 수정 (@etc)
### `/layouts/default.html`
`<body>`의 `<div  class="layout">`를 수정하여 `aboutme`, `skills` 등의 순서를 변경할 수 있음

## CSS 등 디자인 수정
### 전체적인 디자인
`main.min.css`에 따라서 전체적인 디자인이 바뀜 (`main.scss`는 영향 안 줌)
`main.scss`보고 `main.min.css` 수정하면 편함.
{: .notice--success}

`#ff073a` -> `#229756` <br>
`font-family `변경 <br>
line-height:2rem 중간에 넣어주면 행간 커짐 <br>
`Skills` 색 변경 <br>
그 외 여라가지 변경 됨
{: .notice}

### 첫 화면 particles
`/assets/particles.json`에서 `color` 수정
```json
{
  "particles": {
    "number": {
      "value": 10,
      "density": {
        "enable": true,
        "value_area": 800
      }
    },
    "color": {
      "value": ["#e64a4a"]
    },
```
