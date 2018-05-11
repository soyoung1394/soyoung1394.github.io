---
layout: post
title:  "text-overflow"
date:   2018-05-11 20:09:19
categories: others
---
프로젝트를 진행할 때 프로필을 구현하면서 자기소개를 넣을 때 글이 너무 많기보다는 어느 정도가 되면 그 뒤는 '...'으로 생략을 했으면 좋겠다는 생각을 했었다

위와 같이 ...을 붙이고 싶다면 css에서 이를 도와주는 속성이있다.

`text-overflow: ellipsis;`

하지만 이것만 한다면 적용되지 않을 경우가 있다. 아래 두가지를 더 충족시켜줘야 한다.

1. overflow 속성값이 hidden, scroll, auto일 때
2. white-space:nowrap일 때(이것 말고도 텍스트가 다음 줄로 이동하지 않는 비슷한 경우이면 가능하다.)

overflow 속성은 박스의 내용이 길 때 어떻게 보일지 선택하는 속성인데

- visible은 기본값으로 내용이 더 길어도 그대로 놨두는 것
- hidden은 내용이 넘치게되면 자른다.
- scroll은 내용이 넘치치 않아도 스크롤바가 보인다.
- auto는 내용이 잘릴 때만 스크롤바가 보이는 것을 의미한다.

white-space 속성은 공백을 어떻게 처리할 것이지에 대한 것을 정하는 것이다.
앞서 설명한 nowrap은 공백을 여러개 넣어도 1개만 표시가 되고, 텍스트가 길어도 줄바꿈 되지 않는다.

```
.nickname_bottom p{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space: nowrap
}
```

위처럼 쓴다면 아래와 같이 생략되는 것을 확인할 수 있다.
![default](https://user-images.githubusercontent.com/26562553/39921556-537940c6-5556-11e8-8c8e-d8aa8d463ba3.JPG)
