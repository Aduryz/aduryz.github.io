---
title: Hack font custom
excerpt: alt-hack을 이용한 Hack font custom

categories:
  - otherthings
tag:
  - linux
toc: true
toc_sticky: true

date: 2023-02-16T11:56:09.660Z
last_modified_at: 2023-02-16T11:56:09.660Z
---

{{ page.excerpt }}
{: .notice}

이 포스트의 모든 다운로드 링크는 공식적인 루트의 링크이다.
{: .notice--warning}

# 0. 이 포스트의 의의
`hack`이라는 폰트는 프로그래밍 용으로 많이 쓰이는 폰트로 소위 "프로그래밍 폰트"라고 불리는 것들 중 하나다.

<div  class="notice"  markdown="1">
## 프로그래밍 폰트란?
{: .no_toc }
vs code 같은 ide에서 프로그래밍을 할 때 코딩을 좀 더 편하게 하기 위해 설정하는 폰트이다. 프로그래밍 폰트는 다음과 같은 특징이 있다.

### 1. 문자를 구별하기 쉬워야한다.
{: .no_toc }
코딩을 하다 보면 숫자와 영어, 특수문자를 모두 쓰게 되는데 특히 헷갈리는 문자들이 있다.
대표적으로 `1`,`i`,`l`,`|`이나 `0`,`o` 등이 있다. 이런 문자들이 잘 구분되지 않은 경우엔 가독성이 떨어지고 실수로 다른 문자를 입력하기 쉽다. 따라서 구별이 쉬운 폰트가 좋다.

### 2. 고정폭 폰트여야한다.
{: .no_toc }
고정폭 폰트란 각 글자가 동일한 양의 수평 공간을 차지하는 글꼴을 말한다. 책이나 게시물을 읽을 경우에는 가변폭 폰트가 좀 더 조화로울 수 있으나 프로그래밍 폰트는 조화보다는 가독성과 정확성이 중요하기 때문에 고정폭 폰트를 쓰는 것이 좋다. ~체 폰트가 대표적인 고정폭 폰트이다.

## 대표적인 프로그래밍 폰트들
{: .no_toc }
### Consolas
{: .no_toc }
![Consolas](https://img1.daumcdn.net/thumb/R1280x0.fjpg/?fname=http://t1.daumcdn.net/brunch/service/user/63JW/image/cXjCQO-ze3TXRKoueOQbDyGPsfk) <br>
윈도우에 기본적으로 깔려 있는 폰트로써 범용성이 좋다는 장점이 있다.

### D2 Coding
{: .no_toc }
![D2 Coding](https://futurecreator.github.io/2018/11/12/my-best-programming-font-top-3/d2-coding.png) <br>
네이버에서 제작해서 다른 폰트들과 달리 한글 사용에도 최적화되어 있다는 장점이 있다. 주석 등에서 한글을 사용했을 때 조화롭다. <br>
하지만 개인적으로 자간이 너무 좁고, 설정에서 한글 폰트를 다른 걸로 지정해주면 되기 때문에 좋아하지 않는다.

### Fira Code
{: .no_toc }
![Fira Code](https://futurecreator.github.io/2018/11/12/my-best-programming-font-top-3/fira-code.png) <br>
literacy 능력이 가장 강력한 폰트다. literacy란 `->` 같은 코드를 `→` 처럼 사람이 보기 편하게 바꿔주는 기능이다. 참고로 D2 Coding에도 이 기능이 있다. <br>
개인적으로 literacy가 오히려 가독성에 방해되어 선호하지 않는다.

### Hack
{: .no_toc }
![Hack](https://futurecreator.github.io/2018/11/12/my-best-programming-font-top-3/hack.png) <br>
디자인이 예쁘고 무난하여 많이 쓰이는 폰트다. `,`가 `.`와 구별이 잘 된다는 장점이 있다.

### 여러 폰트의 비교
{: .no_toc }
![https://user-images.githubusercontent.com/12673886/27765091-5df18206-5ea9-11e7-88a7-88d1f8707f74.png](https://user-images.githubusercontent.com/12673886/27765091-5df18206-5ea9-11e7-88a7-88d1f8707f74.png) <br>

나는 이 중 `Hack`을 쓰려고 했으나 몇 가지 마음에 안 드는 점을 발견 했다.
1. `0`의 모양이 `slashed` 이었으면 한다.
2. `1`의 모양이 일반적인 폰트처럼 `noslab` 이었으면 한다.
3. `i`와 `l`의 구별이 쉽게 `i`는 `slab` 이었으면 한다.

이 점들을 충족하기 위해 이 포스트의 과정을 거치게 되었다.
</div>

# 1. alt-hack
이런 불만이 많아 공식적으로 몇몇 문자의 모양만 바꿀 수 있는 툴이 있다. 바로 <a href="https://github.com/source-foundry/alt-hack" target="_blank" rel="noreferrer noopener">alt-hack</a>이다. <br>

공식 독스에 잘 설명되어 있긴 하지만 나는 `linux` 명령어가 익숙하지 않아 여러 시행착오를 겪으면서 윈도우에서 빌드하게 되었다. 그 과정을 포스팅하려 한다.

# 2. Download the Hack typeface source
빌드를 위해선 필수적으로 `Hack typeface source`가 필요하니 [다운](https://github.com/source-foundry/Hack/archive/master.zip)받는다. `Hack` 폰트의 원래 source이다.

# 3. Download alt-hack repository
수정하기 위한 `*.glif`들과 수정을 좀 더 편하게 할 수 있는 툴을 [다운](https://github.com/source-foundry/alt-hack/archive/refs/heads/master.zip)받는다. 내가 원하는 수정할만한 모양들이 있는 `*.glif`들과 Overwrite를 좀 더 쉽게 할 수 있게 해주는 툴이 있다.

# 4. Download GNU Make
윈도우에서 `Makefile`이라는 파일을 `make`가 해석하여 프로그램 빌드를 수행할 수 있도록 `GNU Make`를 다운받는다. <a href="http://gnuwin32.sourceforge.net/packages/make.htm" target="_blank" rel="noreferrer noopener">여기</a>서 아래 이미지의 부분을 다운받으면 된다. <br>
![GNU Make](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FckGjTA%2FbtrK3XpDldq%2FNuIGasIt95QQQ0vISvN0c1%2Fimg.png)<br>
이제 `Git`에서 명령어를 수행할 수 있게 되었다. (`Git`말고 `cmd`에서 해도 된다.)

# 5. *.glif Overwrite
`/alt-hack repository`에서 변경하고 싶은 문자의 `*.gilf`파일을 고르고  `/Hack typeface source/source`의 `*.gilf`를 `/alt-hack repository`의 `*.gilf`로 Overwrite한다. 4종류의 폰트 중 원하는 것만 바꿔도 된다.<br> 
`/alt-hack repository`의 `patch-hack.sh`를 이용하면 더 쉽게 Overwrite할 수 있다. 사용 방법을 잘 모르겠다면 그냥 Drag&Drop으로 Overwrite해도 된다.

# 6. Build
`/Hack typeface source`에서 
```
$ make build-with-dependencies
```
명령어를 실행하여 필요한 dependencies를 모두 다운받는다.

그러면 `make`도 같이 실행되어 폰트가 생성된다.

모든 과정이 정상적으로 이루어졌다면 `/Hack typeface source/build/`에 `*.ttf`와 web fonts가 생성되었을 것이다.

하지만 `ttfautohint`의 dependencies 문제로 에러가 발생하는 경우도 있을 것이다. 그렇다면 dependencies를 수동으로 다운 받아서 과정을 완료하는 방법도 있지만, <span style="color:#e64a4a">`*.ttf`만 필요한 경우라면 `/Hack typeface source/master_ttf`에 `*.ttf`가 정상적으로 생성되었으니 그것을 이용하면 된다.</span> <br>
에러를 해결하는 방법은 <a href="https://github.com/source-foundry/Hack/issues/482" target="_blank" rel="noreferrer noopener">여기</a>를 참조해도 좋다. 

원하는 결과물을 얻었으면 다음의 명령을 실행하여 Uninstall한다.
```
$ pip uninstall fontmake && pip uninstall fonttools && rm -rf ~/ttfautohint-build && rm -rf ~/sfnt2woff-zopfli-build && rm -rf ~/woff2
```
