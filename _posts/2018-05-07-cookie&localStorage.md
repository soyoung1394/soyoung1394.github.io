---
layout: post
title:  "cookie & localStorage"
date:   2018-05-05 18:34:10 
categories: home
---
웹페이지에서 데이터를 저장하는 방법은 cookie와 webStorage(localStorage, sessionStorage) 두가지방식이 있습니다.


#### **cookie란?**
웹 사이트에 접속해서 로그인을 하고 난 후, 다시 접속을 하였을 때 사이트에 더 쉽게 접근했던 경험을 한 적이 있을 것이다
그것이 cookie 때문이다. cookie는 웹사이트에 접속할 때 생성되는 정보를 담은 임시 파일이라 할 수 있다.
HTTP는 connectless 방식, 즉 서버에 연결하고, 요청해서 응답을 받으면 연결을 끊어버리기 때문에 클라이언트의 이전 상태를 알 수가 없다.
이런 것을 해결하기 위해서 cookie를 이용한다.
쿠키는 웹 브라우저가 방문했던 웹 사이트에 대한 정보, 로그인 아이디, ip주소 등을 기록하기 때문에 개인 사생활 정보 등을 침해할 수도 있다. 이러한 문제로 보안상의 문제를 조금이나마 해소하기 위해서
웹 브라우저 자체에 쿠키 거부 기능이 있다.


#### **쿠키와 localStorage의 차이점**
쿠키의 저장 공간의 용량은 대략 4KB이다.
localStorage의 저장 공간의 용량은 대략 5MB이다.
쿠키는 서버측과 클라이언트측 양쪽에서 쿠키 데이터를 사용하는 api가 존재
localStorage는 오직 클라이언트측에서만 동작한다.
쿠키는 매번 서버로 전송되어서 저장된 데이터가 클라이언트에만 존재하는 localStorage는 네트워크 트래픽 비용을 줄여준다는 장점이 있다.
쿠키는 만료일을 함께 설정해 일정 시간이 지나면 저장된 데이터를 사용할 수 없게 한다
localStorage는 사용자가 임의로 삭제하지 않는 경우 삭제되지 않는다.
localStorage는 단순 문자열을 넘어 객체정보를 저장할 수 있다
참고로 sessionStorage는 localStorage와 다르게 창을 닫으면 데이터가 초기화가 된다.

#### **localStorage**
값 저장 : localStorage.setItem(key,value)
값 불러오기 : localStorage.getItem(key)
키 열거 : localStorage.key()
항목의 수 : localStorage.length
삭제 : removeItem(key) / clear

*clear 메서드는 localStorage의 모든 것을 삭제한다.
좀 더 복잡한 형태의 데이터를(배열 등) 저장할 때는 JSON.stringify를 사용해서 저장하기 전에 자바스크립트 객체를 사용해서 이를 문자열로 변환하고,
 불러올 때는 JSON.parse를 사용해서 다시 객체로 되돌려놓는다.
