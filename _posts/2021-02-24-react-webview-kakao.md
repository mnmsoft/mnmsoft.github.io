---
title:  "react 에서 kakao undefind"
excerpt: "react 에서 카카오 script가 안될때."
toc: true
toc_sticky: ture
categories:
  - react
tags:
  - react
  - kakao
  - webview
  - android
  - hybrid
last_modified_at: 2021-02-24T18:00:00+09:00
---


# react kakao 라이브러리를 사용하는데 undefined가 나올때


``` js
<script src="//developers.kakao.com/sdk/js/kakao.js">
```


public/index.html 내부에 위 태그를 써서 kakao sdk 를 사용하고 있었다.

리엑트 컴포넌트에서 Kakao 가 undefined 여서 검색해보니 ```window.Kakao``` 를 사용하라고 한다.

잘된다 크롬에서 잘 돌아간다.

그래서 webview에 올려서 테스트 하는데 또 안된다ㅠ

검색을 해보니 나같은 사람이 있는거 같다.. 검색...검색.. 3시간 가까이 시간낭비후에

결과를 얻어냈다...

``` js
<script src="https://developers.kakao.com/sdk/js/kakao.js">
```
``` //~ ``` 로 url을 적으면 알아서 맞게 변환해준다고 하여 여태껐쓰고 있었는데
안드로이드 webview에서는 안되나 봅니다.

3시간을 고생해서 찾아냈는데... 왠지 예전에도 이것 때문에 고생한적이 있는 느낌..

이제는 다시 이걸로 고생하지 말자!!!

끝.



