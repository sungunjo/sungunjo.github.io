---
layout: post
disqus_disabled: false
title: "[HTML5 & CSS3] CSS 와 cascading"
date: 2020-05-28T13:58:00+09:00
author: Jo
categories: html-css
tags: html html5 css css3 web design css style style-sheet cascading 
cover: "/assets/instacode.png"
---

## 1. Cascading Style Sheet(CSS)
### 1. Cascadnig 이란?
위에서 아래로 흐른다는 뜻으로, CSS 의 경우 스타일 시트에서 selector 에 여러 스타일이 적용될 때 스타일 충돌을 막기 위해 '위에서 아래로 흐르며 적용되는' 방법을 사용하는 것을 말한다.<br>
스타일 시트에서 캐스캐이딩은 가장 기본적인 개념이기 때문에 보통 스타일 시트라고 하면 Cascading Style Sheet(CSS) 를 의미한다.<br>
<br>

### 2. 캐스캐이딩의 원칙
  1. **스타일 우선순위**<br>
  스타일 규칙의 중요도, 적용 범위에 따라 우선순위가 결정되고, 그 우선순위에 따라 위에서 아래로 스타일이 적용된다.<br>
  2. **스타일 상속**<br>
  태그들의 포함 관계에 따라 부모 요소의 스타일을 자식 요소로, 위에서 아래로 전달<br>
<br>
<br>

#### 1. 스타일 우선 순위
중요도, 적용 범위, 소스 순서까지 세 가지 우선순위를 차례대로 비교해서 스타일이 적용된다.<br>
<br>
##### 1. 중요도에 따라
<img src="/assets/img/css_cascading/css_priority.png">

  * **User CSS**: 시스템에서 만든 스타일로, 사용자가 제어할 수 없음
  * **Author CSS**: 웹 사이트를 만들 때 제작자(author) 가 만든 스타일
  * **Browser CSS**: 웹 브라우저의 기본 스타일
  * **중요 스타일**: 속성 뒤에 !important 키워드가 붙은 스타일 (ex. `background-color:green !important;`)

위 이미지에서 볼 수 있듯 User CSS 중에서도 중요 스타일이 가장 먼저 적용되고, 그 다음으로 Author 의 중요 스타일, Author 의 일반 스타일, User 의 일반 스타일이 적용된다.<br>
그 후에 가장 마지막으로 남은 부분에 대해서 브라우저의 스타일이 적용된다.<br>
<br>

##### 2. 적용 범위에 따라
<img src="/assets/img/css_cascading/css_priority2.png">

  * **inline 스타일**: 해당 속성 사용된 요소에만 적용
  * **id 스타일**: 해당 id 가진 태그에만 적용
  * **class 스타일**: 해당 class 속성값 가진 요소들 모두 적용
  * **tag 스타일**: 해당 tag 에 전부 적용

말 그대로 스타일이 적용 되는 범위가 좁은 것 부터 큰 것 순서대로 적용된다.<br>
요소의 속성값으로 스타일을 적용해서 단 한 부분에서밖에 사용될 수 없는 inline 스타일이 가장 먼저 적용되고, 기본적으로 selector id 값 가지는 요소 하나에만 적용되는 id 스타일 (만약 같은 id 여러개라면 여러번 사용될 수도 있음), selector 로 사용한 class 를 속성값으로 가지는 모든 요소들에 적용되는 class 스타일, 하나의 tag 타입 요소 전부에 스타일을 적용시키는 tag 스타일 순서대로 적용된다.<br>
<br>

##### 3. 소스 순서에 따라
중요도, 적용 범위가 같다면 소스상 순서에 따라서 결정된다.<br>
소스에서 나중에 나온 스타일이 먼저 나온 스타일을 덮어쓰는 방식이다.<br>
<br>
<br>

#### 2. 스타일 상속
~~~html
<head>
  <style>
    #style-inherit {
      font-family:"궁서";
      color:yellow;
      background-color:brown;
    }
    p.no-inherited {
      font-family:"돋움";
      background-color:black;
    }
  </style>
</head>
<body>
  <div id="style-inherit">
    <p>스타일 지정 안된 자식</p>
    <p class="no-inherited">스타일 지정된 자식</p>
    <div>
      <ul>
        <li>자식 리스트 1</li>
        <li>자식 리스트 2</li>
      </ul>
    </div>
  </div>
</body>
~~~
<head>
  <style>
    #style-inherit {
      font-family:"궁서";
      color:yellow;
      background-color:brown;
    }
    p.no-inherited {
      font-family:"돋움";
      background-color:black;
    }
  </style>
</head>
<body>
  <div id="style-inherit">
    <p>스타일 지정 안된 자식</p>
    <p class="no-inherited">스타일 지정된 자식</p>
    <div>
      <ul>
        <li>하위 리스트 1</li>
        <li>하위 리스트 2</li>
      </ul>
    </div>
  </div>
</body>

자식 요소에서 별도로 스타일을 지정하지 않을 경우 부모 요소의 스타일이 자식 요소로 상속된다.<br>
단, 부모 스타일의 모든 속성이 상속되지 않고, 일부만 전달된다 (ex. 글자 색은 상속 되지만 배경색은 상속 안됨)<br>
위 예시에서 상속받은 \<h1\>, \<ul\>, \<li\> 요소들이 배경색도 전달받은 것 처럼 보이지만 이는 기본 배경색이 투명이기 때문에 부모인 \<div\> 의 배경색이 그대로 보여서 그런 것이다.<br>
부모 요소로부터 스타일을 상속받았는데 자식 요소에서 다른 스타일을 사용하고자 하여 스타일 충돌이 발생한다면 '중요도', '적용 범위', '소스 순서' 등에 따라 우선 순위가 결정된다.<br>
\<p class="no=inhertied"\> 의 경우 따로 지정해준 스타일이 있어서 부모의 font 를 물려받지 않았고, 글자색은 지정되지 않았기에 이 것만 상속받은 것이다.<br>
<br>
<br>

## 2. CSS 모듈
CSS3 는 CSS2 를 기본으로 하여 새로운 규약들을 추가한 것이다.<br>
CSS2 까지는 모든 스타일 규약이 하나에 담겨있어서 굉장히 복잡했고, 업데이트 하기 어려운 단점이 있었다.<br>
따라서 CSS3 에서는 배경, 글꼴, 박스 모델 등 수십 개의 기능을 주제로 별도 규약을 따로 만들어 개별적으로 개발하였으며, 이 별도 규약들을 **CSS 모듈** 이라고 부른다.<br>
<br>

### 브라우저 접두사
CSS3 에서 아직 개발이 진행중이라 표준 규약이 아닌 속성들은 브라우저별로 다른 방식으로 지원된다.<br>
따라서 이러한 속성들은 이름 앞에 prefix 를 붙여서 브라우저별로 구분해줘야 한다.<br>
표준 규약이 완성된 속성도 구 버전 브라우저 사용자를 고려해 브라우저 접두사를 붙이기도 한다.<br>
* **-webkit-**: 웹킷 방식 브라우저(사파리, 크롬 등)
* **-moz-**: 게코 방식 브라우저(모질라, 파이어폭스 등)
* **-o-**: 오페라 브라우저
* **-ms-**: MS 인터넷 익스플로러