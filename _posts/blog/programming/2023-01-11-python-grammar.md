---
title: 공학도를 위한 창의적컴퓨팅 - 문법
excerpt: 공학도를 위한 창의적컴퓨팅을 수강하면서 정리한 Python 문법

categories:
  - programming
tag:
  - python
toc: true
toc_sticky: true

date: 2023-01-11T11:56:09.660Z
last_modified_at: 2023-01-11T13:18:24.961Z
---

{{ page.excerpt }}
{: .notice--info}

# Python 문법

생성일: 2023년 1월 11일 오후 9:09

# 주석

`#`을 앞에 붙여서 정의

용도는 설명이나 버그 찾기

# 연산식

| +, -, *, / | 사칙연산 |
| --- | --- |
| // | 몫 |
| % | 나머지 |
| ** | 승 |
| abs(숫자) | 절댓값 |

# 변수

`변수명 = 값` 으로 정의

## Casting

`int(~)` 문자 or float → int

`float(~)` 문자 or int → float

`str(숫자)` 숫자(int, float) → 문자

`invalid literal for int() with base 10:` 이 에러가 난다면 ()안에 있는 게 int로 바꿀 수 없는 거임, c1이라던가 4.3이라던가

## 증감식

`a += 1` 사칙연산 다 됨, 초기값 설정해줘야함

# 출력

`print(var or val, ... , end = '형태')` 콤마 사이사이 띄어쓰기 있음

`print('%format' %(val)`

`%d`  int 

`%e`  exp. 

`%.2f` 소수점 2번째짜리까지 출력(6에서 반올림)

`/n` CR

`/t` tab

# 입력

`변수 = input('메세지')` 무조건 문자로 입력됨

`int(input(' '))` 으로 casting 가능

# 리스트 옵션

| : | slice, 마지막거는 포함 안 됨, :만 있으면 전체 |
| --- | --- |
| range(int) | 얘로 생성한 리스트는 수정 불가, 0~마지막-1까지 생성range(1, 10, 2)처럼 시작, 끝(포함X), 간격 설정 가능, 안에는 무조건 int가 있어야함, float도 안 됨 |
| del list[idx] |  idx번째 값을 삭제, 속도 저하 발생 |
| list.append(val) |  val을 마지막에 추가, 속도 저하 X, a.append([1,2]) 처럼도 가능 |
| list.sort() |  오름차순으로 정렬 |
| list.reverce() |  리스트 배열을 거꾸로 |
| list.index(val) |  val이 있는 자리의 index를 찾는다(복수일 경우 첫번째만), int로 리턴 |
| len(list) |  list의 총 길이, [0,1,2,3]의 길이는 4, len(a[1]) 처럼도 가능 |
| list.insert(idx, val) | idx위치에 값을 삽입, 비효율적 |
| list.remove(val) | 값을 삭제 (복수일 때는 처음 값만) |
| list.count(val) | val을 포함하고 있는 수 (val이 몇 개냐) |
| list.extend(list1) |  list에 list1을 추가, 얘는 append와 다르게 차수가 달라지지 않음 |
| var = str.replace('전', '후') |  |
| var = str.split('형태') |  형태를 기준으로 자르고 리스트화 시켜서 var에 저장

___1,_865,_656(_는 공백) 이런건 _말고 ,로 split해야함, _로 하면 앞에 다 split됨 |
| var = '형태'.join(list) |  문자만 가능 |

# 조건문, 반복문 - 유용한 것들 위주로

`a = 1`, `if(a):` 이러면 실행됨

`while`에서 변수의 증감식 무조건 있어야함

`while(1)` 무한반복, break으로 끝내거나 안에 조건을 넣어서 끝낼 수도 있음

`for i in range(len(a))`

`continue` `break` 루프 하나에만 적용됨

# 기타

`문자열A in 문자열B` → 문자열 A가 B에 포함되어 있으면 True

# 함수

return형 함수가 유용할 때가 많음 - 받아주는 애가 있어야 메모리에 무리가 안감

원래 맨 위에서 선언하는 거

return형 함수는 계속 연속해서 사용가능

ex) int(a.readline().split(’ ‘)[1])

but 한 줄에 readline 두 번 하는 실수 주의

## 전역변수, 지역변수

이름만 같고 하나는 지역, 하나는 전역일 수 있음

`grobal var` 로 명시적 전역 변수로 함수 안에 전역변수를 적용시킬 수 있음

함수에서 리스트는 shallow copy로 암시적으로 지역변수 됨

# import

`import 파일이름`

`import 파일이름 as aa` aa로 간략화해서 사용

`from 파일이름 import fn`fn만 가져옴

# 파일입력

`변수 = open('파일이름/확장자', 'r')`

| 변수2 = 변수1.readline() | 1줄만 읽어옴 → str,
프로그램의 끝이 어딘지 알 때 사용,
close하기 전에는 이어서 읽어옴, 중간에 쓸데없는게 있어도 일단 더미에 읽어오긴 해야함,
open하면 다시 처음부터 읽어옴 |
| --- | --- |
| 변수2 = 변수1.readlines() | 모든 줄을 한꺼번에 읽어옴 → list
프로그램의 끝이 어딘지 모를 때 사용, 메모리에 무리가 갈 수도 |
| 변수2 = 변수1.read() |  모든 줄을 한꺼번에 읽어옴 → str |

`변수1.close()` 꼭 닫아줘야함

`* `c = b[0].split(' ')` → [’1’, ‘2’, ‘3\n’] → `int(3\n)` → 3

int로 casting할 때는 안에 공백이든 뭐든 다 없애고 바꿔줌

# 파일 출력

`변수1 = open(‘파일이름.확장자’, ‘w’)`

`변수1.write(변수 또는 형태)` 

()안에는 str만 들어갈 수 있음 - str(변수) 이런식으로 바꿔서 +로 합쳐서 출력해야함

ex) `wt.write(str(domain[j][i])+' ')`

`wt.write('\n')` 으로 엔터

`변수1.close()`