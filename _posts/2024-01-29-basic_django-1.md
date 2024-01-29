---
layout: post
title: Basic Django 1
subtitle: learn basic django
author: Samiiz
categories: [Python, django]
banner:
  image: "posting_images/django/django.png"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: [Python, django, basic]
---

## django
<br/>

django란 Python의 오픈소스 웹프레임워크이며 풀 스택 프레임워크입니다.  
오늘은 django를 사용하는데 필요한 기초 지식과  
사용하면서 느낀점을 적어보려고 합니다.

<br/>

### 설치
<br/>

설치를 하는 방법은 생각보다 간단합니다.  
(저는 애플 실리콘 맥북이기 때문에 맥OS 기준으로 설명하겠습니다.)


#### 가상환경
<br/>

가상환경에서 pip를 사용하여 설치하려면 터미널을 열고,

```zsh
pip install django
```

이렇게 코드를 입력하여 실행하면 됩니다.  


#### Python버전
<br/>

Python 버전별로 설치를 할 수 있습니다.  
터미널을 열고,

```zsh
python install django
python3 install django
```

이렇게 코드를 입력하여 실행하면 됩니다.


### 실행
<br/>  

[설치방법](#설치)으로 django를 설치 한 후  
프로젝트를 생성하려는 위치에서 터미널을 열고,  

```zsh
djanggo-admin startproject {시작하려는 프로젝트 이름}
# 보통의 경우 'config .' 으로 사용한다.
djanggo-admin startproject config .
```

이렇게 코드를 입력 시 해당 프로젝트의 이름은 한 python파일과 폴더가 생성됩니다.  
예를 들어 'config .' 으로 진행 시 'manage.py'와 'config'폴더가 생성됩니다.  
이제 터미널에서  

<br/>

```zsh
{설치시 사용한 방법} manage.py runserver
# 저는 python3로 설치하였기 때문에
python3 manage.py runserver
```

이렇게 실행시  

```zsh
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
January 29, 2024 - 04:34:21
Django version 5.0.1, using settings 'config.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```

이런 문구가 나옵니다.  
간단하게 설명하자면

```
'manage.py'가 실행되었고 마이그레이션이 안되어있다.(현재는 무시해도 무관)  
실행시간, django의 버전, 로컬의 8000번 포트에서 실행중, CONTROL-C를 이용해 종료 가능
```

입니다.  

#### 브라우저 확인
<br/>

자 이제 브라우저 주소창에 ["http://127.0.0.1:8000/"](http://127.0.0.1:8000/)를 입력하고 들어가면

<img src="https://github.com/Samiiz/Samiiz.github.io/blob/master/posting_images/django/django-none.png?raw=true" width="600px" height="400px">

이런 화면이 나오게 되면 성공입니다.  
자 이제 터미널로 돌아가서 "CONTROL + C" 를 입력하여 서버를 종료합시다.

<br/>

## 마치며
<br/>

이번 포스팅에는 Django가 무엇인지, 어떻게 설치하고 어떻게 실행하는지에 대해 알아보았습니다.  

저는  django를 배우고, 사용해보면서 어렵지만  이미 완성되있는 프레임워크를 사용하기 때문에  
기초지식과 내가 사용해야하는 부분만 잘 알고있다면 정말 간단하고 멋진 웹을 만들 수 있겠구나 생각했습니다.  

> <u>배움은 젊음의 샘이다.
> 아무리 나이가 많이 들었더라도 배움을 멈추지 마라. -도교</u>

다음 포스팅에는 서버를 실행하고,  
간단하게 서버에 다양한 화면들을 만들어 보도록 하겠습니다.