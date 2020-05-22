---
layout: post
disqus_disabled: false
title: "[HTML5 & CSS3] 웹 공부 내용 정리 1 - HTML 의 기초"
date: 2020-05-22T15:53:00+09:00
author: Jo
categories: html-css-summary
tags: html html5 css css3 web
cover: "/assets/instacode.png"
---

## 1. HTML?
텍스트, 이미지, 링크 등 여러 요소를 다루고 표시할 수 있는 웹 문서 제작 언어  
  

## 2. 웹 표준?
웹 사이트를 만드라 때 지켜야 하는 약속들을 말한다.  
표준을 지켜 제작해야 어떤 기기, 브라우저에서나 웹 사이트를 사용할 수 있다.  
  
현재 HTML5, CSS3 가 최신 웹 표준이며, 이 둘을 사용하면 사용자 접속 기기에 따라 사이트 레이아웃 다양하게 바꿀 수 있다.  
또한 HTML5 를 이용하면 예전처럼 flash player 없이도 인터랙티브한 사이트를 만들 수 있다.  

html5의 API 사용해서 웹 앱을 만들 수도 있다. 앱의 화면은 HTML5, CSS3 사용해서 디자인 한다.  
  
  
  
## 3. HTML 문서 기본 구조
~~~html
<!doctype html>
<html> 
  <head>
     <meta charset="utf-8">
     <title>Hello, World!</title>
  </head>
  <body>
    <h1>Hello</h1>
    <p>World</p>
    <img src="images/hello.jpg">
  </body>
</html>
 ~~~  
   
### 1. \<!doctype html\> - HTML 문서와 DOCTYPE
HTML 문서는 가장 첫 부분에 \<!doctype html\> 키워드를 써서 doctype(Docuent Type) 선언을 해줘야 한다.  
이게 있어야 웹 브라우저가 웹 문서의 버전을 확인하고 그에 맞게 해석해서 브라우저에 표시해줄 수 있다.  
  
  
### 2. \<html\> 태그 - 웹 문서의 시작
\<html\> ~ \</html\> 을 써서 웹 문서의 시작과 끝을 나타낸다.  
웹 브라우저가 \<html\> 태그 만나면 \</html\> 까지의 소스를 읽어서 HTML 문법에 따라 브라우저에 표시한다.  
\<html lang="ko"\> 처럼 lang 이라는 속성을 이용해서 문서에서 사용할 언어를 지정할 수 있다.  
\<html\> 태그 안에 \<head\>, \<body\> 부분이 포함된다.  
  
  
### 3. \<head\> 태그 - 브라우저에게 해석 정보를 제공
웹 브라우저가 웹 문서를 해석할 때 필요한 정보들을 입력하는 부분이다.  
스타일 및 스크립트 등이 포함되기도 하며 문서에서 사용할 외부 파일들 링크도 여기에 들어간다.  
  
* \<title\> 태그: 브라우저 제목 표시줄에 표시됨. 이 외의 내용은 표시 안됨
* \<meta\> 태그: 문자 인코딩 방법 및 문서의 키워드, 요약 정보를 지정
  
  
4. \<body\> 태그 - 문서의 몸통
실제로 웹 브라우저 화면에 나타날 내용들을 입력하는 부분이다.  
위 예시의 \<h1\>, \<p\>, \<img\> 와 같이 대부분의 태그들이 \<body\> 태그 안에서 사용된다.  
  
  
> 특수기호 입력
특수기호를 그냥 입력해서는 제대로 브라우저에 표시할 수 없다.  
예를들어 < 를 태그가 아니라 꺾쇠 괄호 그 자체로 표시해 주고 싶으면 < 대신 `&lt;` 를 사용해야 한다.  












