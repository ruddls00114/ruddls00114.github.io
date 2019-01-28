---
layout:     post
title:      "express를 사용하여 node 서버 구축하기[1]"
subtitle:   "express 프레임워크의 정의와 설치방법, 구성을 알아보자."
date:       2019-01-28 14:26:00
author:     "kyoungIn"
header-type: "text"
tags:
    - nodeJS

---

# express를 사용하여 node 서버 구축하기 1



### express란?

http 요청에 대하여 라우팅(routing) 및 미들웨어(middleware)기능을 제공하는 웹 프레임워크

  라우팅:어플리케이션 서버에서 경로를 제어하는 목적으로, 목적지까지 갈 수 있는 여러 경로 중 한가지 경로를 설정해주는 과정

 미들웨어:미들웨어는 양 쪽을 연결하여 데이터를 주고받을 수 있도록 중간에서 매개 역할을 하는 소프트웨어, 네트워크를 통해서 연결된 여러 개의 컴퓨터에 있는 많은 프로세스들에게 어떤 서비스를 사용할 수 있도록 연결해주는 소프트웨어를 말한다.

### express 설치

- express-generator 설치 : npm install -g express-generator 
- express 프로젝트 생성 : express project_name && cd project_name
- npm 모듈 설치 : npm install 



### 구성

bin : 프로그램 실행과 관련된 파일이 들어있는 폴더. 내부에 있는 www 파일을 실행에서 프레임워크를 실행. port번호 지정

node_modules : 이 express폴더에 필요한 모듈 저장된 폴더.

public : image,js,css 와 같은 정적인 파일 관리

**routes** : url 별로 수행되는 실제 서버의 로직 처리.  index.js 파일로 라우팅 관리.

views : html, jade,ejs 와 같은 웹 페이지를 관리

app.js : 이 프로젝트의 메인 소스코드. 미들웨어 설정. 라우팅의 시작.