---
layout: post
title: Web Crawling
subtitle: about Web Crawling
author: Samiiz
categories: Python
banner:
  image: "posting_images/big_python.png"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: [Python, Crawling]
---

# Web Crowling
## 웹 크롤링(Web Crawling)
**웹 크롤링이란 웹상의 정보들을 탐색하고 수집하는 작업을 의미합니다.**  
  
"개발자 도구"를 사용해본 경험이 있으십니까?  
  
저는 자주 사용하는 네이버와 구글 사이트에서 개발자 도구를 처음 실행시켰을 때 머리가 아팠습니다.  
당연히도 제가 로컬에서 만든 아주 간단한 HTML파일과는 차원이 달랐기 때문입니다.  
그 안에는 방대한 양의 정보들이 담겨있었고 또 우리는 볼 수 없는 정보들도 있었습니다.  
그러한 정보뭉치들 사이에서 원하는 정보를 바로바로 찾고 가져오기란 쉽지 않습니다.

그래서 웹 크롤러(Crawler)가 생겨났습니다.

### 크롤러(Crawler)
**크롤러**는 화면에 노출된 정보를 수집해주는 소프트웨어입니다.  

자세히 말하자면  
크롤러는 웹상을 돌아다니며 방대한 양의 정보들을 수집하고  
실시간으로 정보를 수집하기 위해 지속적으로 작동되어  
**특정 키워드**에 대한 **심층분석**에 유용하고 **자주 변화하는 데이터**를 파악하기에 좋습니다.   

그러므로 크롤러를 이용하면      
개발자도구의 요소선택기를 사용하여 원하는 정보들을 일일히 확인하고 파악해서  
하나하나 정보를 타이핑 하는 일은 없어집니다.

### 주의!    웹 스크래핑 != 웹 크롤링
  
웹 스크래핑은 웹 크롤링과는 다른 개념이므로 표현에 주의해야 합니다!  

웹 스크래핑은 **스크래퍼 봇**을 통하여 특정 웹에서 필요한 데이터를 자동으로 수집하는 것 입니다.  
정확한 정보를 요구할때 사용합니다.  
  
  
**웹 크롤링과 웹 스크래핑의 차이점**  

![table](/posting_images/크롤링%20스크래핑%20차이.png "table image")



