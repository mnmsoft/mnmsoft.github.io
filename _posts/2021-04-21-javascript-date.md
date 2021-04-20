---
title:  "javascript 한국시간"
excerpt: "javascript datetime 다루기"
toc: true
toc_sticky: ture
categories:
  - javascript
tags:
  - javascript
  - new date
  - 타임존
  - timezone
  - 한국시간
last_modified_at: 2021-04-12T02:00:00Z
---


# javascript 에서 DateTime 사용하기.

asp 나 mssql 만 자주 사용했던 old한 개발자여서..
javascript에서 datetime 을 다룰일이 별로 없었다.

그러다가 요즘 javascript를 공부하면서 timezone 에 대한 이슈가 있는것을 알고있지만 외우가나 이해하지 못해서 매번 사용할때 마다
구글검색을 하고 있는 내모습을 보고 한번 정리해본다.

내가 자주 사용하는 처리방식은 아래와 같다.
- 한국시간을 표시하거나 디비에 넣기 위해 문자열로 만들기 
- 구해진 시간을 더하거나 빼기 (DateAdd)
- 구해진 시간을 비교하기 

일단 기본적으로 javascript에서 new Date() 를
하게 되면 원하는 결과가 나오지 않는다.
현재시간이 2021-04-21 오전 02시 10분인데..
``` javascript
console.log(new Date()) // 2021-04-20T17:10:43.573Z
```
결과는 9시간 빠르게 나온다.
우리나라가 gmt+9 라서 그런가 보다.

그래서 우리나라에 맞게 처리하기 위해서 시간을 +9 해서 처리하기로 했다.

``` javascript
const korDate = () => {
    const myDate = new Date()
    return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds());
}
```

일단 한번 new Date() 로 시간을 구한다음
그 시간을 기준으로 년,월,일,시,분,초 를 구하고
시 + 9 해서 다시 new Date 를 한다.
그러면 날짜가 넘어가도 자동으로 계산되어서 한국시간을 가져올수 있다.


그리고 한국시간을 기준으로 dateAdd 를 하는 함수를 만들었다.
매개변수로 넘어온 한국시간을 가지고 하는것도 쉽게 응용이 가능할것이다.
``` javascript
const korTimeAdd = (gubun , number) =>{
  
    const myDate = new Date()
    
    switch (gubun) {
      case "y":
        return new Date(myDate.getFullYear() + number , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds() )
      case "M":
        return new Date(myDate.getFullYear()  , myDate.getMonth() + number, myDate.getDate() , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds() )
      case "d":
        return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() + number , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds() )
      case "h":
        return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9 + number , myDate.getMinutes() , myDate.getSeconds() )
      case "m":
          return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9 , myDate.getMinutes() + number , myDate.getSeconds() )      
      case "s":
        return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds() + number )
      case "ss":
          return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds() , myDate.getMilliseconds() + number)            
      default:
        return new Date(myDate.getFullYear() , myDate.getMonth() , myDate.getDate() , myDate.getHours() + 9, myDate.getMinutes() , myDate.getSeconds() )
    }
}
```

첫번째 인자로 년도,월,일,시,분,초,밀리초 인지 구분을 하고 (월의 month 와 분의 minute 가 겹쳐서 대문자 M 이 월이다.)
두번째 인자로 얼마만큼 더해질지 숫자를 쓰면 된다. (음수를 써도 될것이다.)

시간비교는 >,< 인 비교 연산자로 처리가 가능한것으로 보여서 생략한다.

이만..


