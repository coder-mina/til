# Static Site Generator

## 알게 된 것

* 공식 문서를 제대로 읽고, 안 되는 부분들을 검색하는 것이 훨씬 빠르다...
* 

## Hexo



## Jekyll

## Jekyll이란...

* raw text file을 static website로 convert해주는 것. (by rendering Liquid, Markdown, and other transforms)

* jekyll은 템플릿 언어로 Liquid를 사용함.

## Liquid이란...

* Shopify에 의해 개발되고 Ruby로 작성된 오픈소스 템플릿 언어. (템플릿 언어 = 문장이 코드를 감싸는 식으로 동작하는 언어.)
* https://blog.turastory.com/template-language-and-liquid/
* 세 가지 개념
  * object: 컨텐츠를 보여줄 때, 변수명을 둘러싸는 {{ }} 형태로 표현됨. ex) {{ site.title }}
  * Tag: 제어의 흐름 결정, {%로 시작되고 %}로 끝남.  ex) {% if site.posts.size >= 10 %}
  * filter: liquid object의 결과에 변형을 가할 때 ex) {{ "/blog/" | absolute_url }}

* [paths](https://stackoverflow.com/questions/23992546/html-not-loading-css/23992979)
* 