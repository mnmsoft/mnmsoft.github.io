---
title:  "react 공부 http통신 fetch vs axios"
excerpt: "http통신 fetch vs axios 로 get하는 방법"
toc: true
toc_sticky: ture
categories:
  - react
tags:
  - react
  - fetch
  - axios
last_modified_at: 2021-01-22T15:00:00+09:00
---


# http통신 ajax처리 

> 일단 get으로 데이터 가져오는 부분만 있다 나머지는 차차...

리엑트를 공부하고 기본문법을 배운다음 무엇인가 실제적으로 작업을 해야지 오래 기억이 날꺼 같아서 몇몇 프로젝트를 진행해보려고 하는데 처음부터 막힌다.

외부의 있는 자료를 가져와서 ui를 그려줘야 하는데 외부 자료를 가져오는 방법을 모르겠다.

그래서 검색하여 테스트하고 나온 결과를 정리해본다.

> 테스트 과정에서 url은 `jsonplaceholder.typicode.com` 로 하드코딩되어 있으니 url파라미터로 사용하면 되겠다.


## fetch get 처리 방식

### 함수구현

``` js
export async function getPost(postId) {    

    let response = await fetch("https://jsonplaceholder.typicode.com/posts/" 
                                            + postId);
    let responseOK = response && response.ok;
    if (responseOK) {
        let data = await response.json();
        console.log("data" , data);
        return data;
    }

```

### 사용
``` js
    let resultData = await service.getPost(3);
    console.log("resultData" , resultData.title);
    const title = resultData.title;
    const body = resultData.body;

```


### 주의할점

라이브러리 설치 없이 사용이 가능하지만 익스플로어에서 사용이 안된다고 한다. 테스트는 안해봤다.

## axios 로 get처리 방식


### 설치
``` 
    npm install axios
```

### 함수구현

``` js
// '/src/services/post'
import axios from 'axios';

export function getComments(postId) {
    return axios.get(`https://jsonplaceholder.typicode.com/posts/${postId}/comments`)
}    
```



### 사용
``` js
// '/src/app'
import * as service from './services/post';

const info = await Promise.all([
    getComments(postId)
])

const comments = info[0].data;
```


프라미스타입으로 반환되는데..
아직 프라미스타입을 잘 이해해자 못하였다.
.then
.catch 를 할수 있는 정도이다.
왜 fetch는 .json 을 하고
axios 는 .data 를 하는지 모른다. 일단 동작은 되니 쓰고 있다!










