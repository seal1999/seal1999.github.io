---
layout: post
title:  "React 개발 스터디 개요"
date:   2020-05-05 21:03:36 +0530
categories: React 
---

*** Modern Javascript** 기반의 프론트엔드 개발 기술을 익히기 위해 2~3개월 단위로 주제와 기술을 변경해 연말까지 3~4회 스터디를 진행하고자 합니다. 네이버 하코사 카페에서 스터디 팀원을 모집하여 함께 진행하고 있으며, 첫번째 스터디할 기술로 React를 정했습니다.

## 개발 대상
- Build A Real World Beautiful Web APP with Angular 8 — A to Z Ultimate Guide (2019)
... which is shown in the screenshot below:
![React eather Application Screenshot](/assets/minus.png)
- 라이브 데모 (V2) : https://minimus-weather.web.app
- 관련 Article : Part 1, 2로 구성되어 있음
- https://medium.com/@hamedbaatour/build-a-real-world-beautiful-web-app-with-angular-6-a-to-z-ultimate-guide-2018-part-i-e121dd1d55e
- https://medium.com/@hamedbaatour/build-a-real-world-beautiful-web-app-with-angular-8-the-ultimate-guide-2019-part-ii-fe70852b2d6d
- Github Repo : https://github.com/hamedbaatour/Minimus

예제가 단순하기 때문에 디자인 영역을 제외한 모든 영역을 직접 개발합니다.
서로 도와줄 수 있도록 가급적 개발 환경, 기술 SET, 버전 등은 통일했으면 하지만 강제는 아닙니다.
학습 목적이므로 ES6 문법의 적절한 사용을 권장하며, 
일러스터, 아이콘 등은 해당 사이트에서 제공되는 것을 사용해 코딩에 집중합니다.
8주 목표 일정으로 진행하고, 4주는 어떤 단계에서 학습할 내용이 많을 수 있어서 Buffer로 남겨둡니다.

   Step 1. 디자인 (Adobe XD) 생략, 개요 소개 및 환경 설정으로 대체 (1day)
      . SVG 아이콘, 일러스터 디자인 등은 그대로 사용
      . 아이덴티티를 위해 파비콘 정도는 각자 다르게 가져가도 좋을 듯 함

   Step 2. 개발 (3day, 1개 기술SET으로 각자)
     ※ 예제는 Angular로 되어 있으나, Vue.js나 React 사용 예정, 첫째날 모여서 결정
     . 개발환경은 VScode로 통일하고, Node 버전은 최신으로, 플러그인은 각자
     . 전 Vue, React 중에서 선택할 생각이고, Typescript를 써보려고 함
     . 컴포넌트 설계 및 스타일은 각자 취향대로 진행하되, 사이트에 소개된 코드를 Pseudo-Code로 참고
     . 날씨 API 연결, UI 서비스(테마)를 위해 Typescript, GraphQL을 맛보기 수준으로 간단히 사용
     ※ 날씨 API는 AERIS의 Weather API를 최신버전(1.11.5)으로 사용 
       (REST API를 제공하고, JSON으로 전달받아 다양한 자바스크립트를 연습하기에 좋을 것 같음)
       https://www.aerisweather.com/support/docs 

   Step 3. 코드 리뷰 및 기능 추가, 리팩토링 (3day, 각자 취향껏/실력껏 기능 및 기술 선택)
     · 기능을 추가하면서 각자 개발한 코드의 확장성, 중복코드 등 검토
       (1) 도시 검색/추가 기능, 
       (2) 일러스터/애니케이션 추가 
       (3) 사용자 인증 
        ※ 예제는 AngularFireLiteAuth를 사용하는데, 각자 원하는 걸로
       (4) 소셜 연계 
        ※ 예제처럼 Twitter API를 연계하던가, 자신의 느낌을 담은 날씨 톡을 Facebook으로 보내는 등 취향껏

   Step 4. 배포 & 정리 (1day, 회고)
      . 예제는 Node Express 서버에서 실행되는 서버사이드 렌더링 방식으로 배포했는데,
        이 방식은 관심이 없어서 vue-cli 라든가 프레임워크에서 제공하는 방식으로 하면 될 것 같습니다.
      . 소스는 github에서 형상관리하고, 히로쿠 사이트에 배포하면 될거 같은데 중요하지 않아서 의논해서 정해요     
         https://www.heroku.com/
         ※ 혹시 공동 코딩을 하게 되면 bitbucket에서 비공개로 하다가 스터디 끝나면 완성된 코드를 github에 공개
