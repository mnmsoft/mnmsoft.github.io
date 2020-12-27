---
title:  "마크다운 기본 문법"
excerpt: "블로그를 운영하기 위해 기본적으로 마크다운(makedown)문법을 알아야 하여 기본적인 내용을 정리해봅니다."

categories:
  - Blog
tags:
  - Blog
last_modified_at: 2020-12-28T05:21:00+09:00
---
  
  
  

제목을 작성하기 위해서는 `# 제목` 을 적는다.

```
기본적으로 제목은 `#` 을 이용하여 작성한다.
```
결과  
# 제목  

`#`의 갯수의 따라 제목을 6개까지 구분할수 있다.  
html의 h1~h6으로 이해하면 된다.

```
# 대제목
## 중제목
### 소제목
```
결과
# 대제목
## 중제목
### 소제목
  
---
  
  
  
  

뛰어 쓰기를 하려면 그냥 엔터만 적는게 아니라  
뒤에 스페이스를 두번 입력해야 한다.  
  
뛰  
어  
쓰  
기

뛰
어
쓰
기

---
  
  
  

밑줄을 표시하기 위해서는 ` --- ` 사용합니다.
```
---
```
---

---
  
  
  

글자를 강조하기 위해서는 글자를 `*,**,~~` 로 감싸면 된다.  
순서대로 이탤릭,볼드,취소선 이다.
```
*글자*
```
*이것은 이탤릭 글자*  
  
```
**글자**
```
**이것은 두꺼운 글자**  
  

```
~~글자~~
```
~~이것은 취소선~~
  
---
  
  
  
  

또 인용문구를 넣기위해서는 `>` 를 사용한다.
> 이것은 인용문구 입니다.
  
---
  
  
  
  
  

` > , >> , >>> ` 를 이용해서 계층을 표현할수 있다.  
  
---
  
  
  
  
  
정렬을 하기 위해서는 숫자를 이용하거나 `-` 를 이용하면 된다.

```
1. 수학
2. 영어
3. 과학
```
1. 수학
2. 영어
3. 과학
  
```
- 수학
- 영어
- 과학
```
- 수학
- 영어
- 과학
  
---
  
  
  
  
소스코드를 작성하려면 ``` 를 사용한다. 


```
``` js
console.log("test console");
```

``` js
console.log("test console");
```
  
    
    
  
---
  
  
  
  

링크를 표현하기 위해서는 `[표시문구](링크주소)` 를 사용합니다.

```
[네이버링크](http://www.naver.com)
```

[네이버링크](http://www.naver.com)
  

링크의 target을 변경하려면 html태그를 이용해야 합니다.  

``` html
<a href="http://www.naver.com" target="_blank">네이버링크</a>
```
<a href="http://www.naver.com" target="_blank">네이버링크</a>

  
---
  
  
  
  

이미지를 넣으려면 `![이미지설명](이미지url)` 을 사용합니다.

```
![엠엔엠로고](http://mnmsoft.co.kr/images/mnmlog.png)
```
![엠엔엠로고](http://mnmsoft.co.kr/images/mnmlog.png)

이미지에 링크를 넣으려면 이렇게 합니다.
```
[![엠엔엠로고](http://mnmsoft.co.kr/images/mnmlog.png)](http://www.mnmsoft.co.kr)
```
[![엠엔엠로고](http://mnmsoft.co.kr/images/mnmlog.png)](http://www.mnmsoft.co.kr)

html을 알고 있다면 html로 하셔도 됩니다.
```
<a href="http://www.mnmsoft.co.kr" target="_blank"><img src="http://mnmsoft.co.kr/images/mnmlog.png"</a>
```
<a href="http://www.mnmsoft.co.kr" target="_blank">
  <img src="http://mnmsoft.co.kr/images/mnmlog.png" alt="엠엔엠로고"/>
</a>

  
---
  
  
  
  

이상으로 마크다운(markdown)기본 문법을 알아봤습니다.
처음에는 어렵게 느껴 질수 있겠는데 포스팅을 작성하기 위해 한두번 작성하고 나면 쉽게 익숙해 질것이라고 생각이 드네요

다음에 또 봐요~












