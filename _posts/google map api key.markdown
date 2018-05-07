---
layout: post
title:  "Google Map Api Key"
date:   2018-05-07
categories: [others]
---
#### **API KEY 가져오기**
안드로이드에서 google Map API를 사용하려면 일단 KEY를 만들어야 합니다. 이 KEY는 상단에 '키 가져오기'를 클릭하여 쉽게 만들 수 있습니다.

#### **SHA-1 인증서 지문**
여기서 조금 시간이 걸렸던 것은 '사용자 인증 정보'에서 'Android앱의 사용량 제한'에서 패키지 이름 및 지문을 추가할 때였습니다.

패키지 이름은 project를 생성하면 쉽게 manifests에서 쉽게 확인을 할 수 있습니다.
SHA-1 인증서 지문은 cmd를 킨 후, .keystore 파일이 있는 곳으로 입력한 후``` keytool -list -v -keystore <이름.keystore>```을 입력하면 됩니다.

대부분 .keysotre파일은 '.android' 폴더 안에 있고 debug.keystore라는 이름을 가지고 있을 것입니다.

``` keytool -list -v -keystore debug.keystore```을 입력하면 sha-1 인증서 지문을 확인할 수 있습니다.

만약 오류가 난다면 자바 환경 변수를 해줘야 합니다.

![2](https://user-images.githubusercontent.com/26562553/39685858-4f349866-5200-11e8-935f-6b62eb91709a.JPG)

path를 편집해서 ```C:\Program Files\Java\jdk1.8.0_91\bin``` 이렇게 jdk에서 bin이 있는 곳까지 경로를 추가해줍니다.

다시 실행해보면 오류가 안나고 실행되는 것을 볼 수 있습니다.
만약 오류가 난다면 cmd를 껐다 키면 실행이 될 것입니다.
