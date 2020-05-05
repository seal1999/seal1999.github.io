---
layout: post
title:  "React 개발 스터디 1일차"
date:   2020-05-06 21:03:36 +0530
categories: React 
---

*** React** 에 대한 사전학습을 빠르게 진행하고, 개발 환경 및 어플리케이션 구조를 잡는 것까지 진행했습니다.

### 개발 환경 같이 가져가기

* 서로 코드를 보며 토론하려면 환경이 비슷해야 좋을 것 같아 맞추기로 함
   * node 12.14.1
   * vscode 1.44.2
   * Extensions (Ctrl + Shit + X를 눌러서 검색 후 설치)
      * reactjs code snippets : 코드스니펫 - rcc, rac 등을 입력하면 react 템플릿을 빠르게 만들어줌
      * Prettier - 코드 인덴테이션 등을 자동 맞춤
      * Material Icon Theme : 디렉토리, 파일유형을 쉽게 인지하도록 아이콘 부여   
   * yarn 1.22.4
   * chrome용 React Developer Tools

### 개발 디렉토리 및 라이브러리 설정 

* npm이 너무 잘 만들어져 있지만, yarn이 조금 더 빠르다고 본 것 같아 yarn 명령을 섞어 사용해봄
* yarn을 써보니 빠르단 건 크게 체감하지 못함, 사용법이 단순해서 필요할때 명령어를 익혀 사용하면 될 것 같음 

### Step 1. React 기본 어플리케이션 생성

* create-react-app을 전역으로 설치하고, hacosa-react-weather란 이름으로 react 어플리케이션 생성
```javascript
npm install -g create-react-app
npx create-react-app hacosa-react-weather 
```
* VScode에서 해당 디렉토리 열고, `Ctrl ~` 명령으로 cmd 창을 띄워 생성된 어플리케이션 실행 및 확인
```javascript
npm start 
```
* cmd 창에서 `Ctrl+C`로 개발서버 중지

### Step 2. 라이브러리 추가 설정

* cmd 창에서 yarn 명령으로 Router와 Redux 사용을 위한 5개 라이브러리 추가
```javascript
yarn add react-router-dom
yarn add redux react-redux
yarn add redux-promise redux-thunk
```

* package.json 을 열어서 정상설치 확인

### 개발 대상 분석 

* Angular로 만들어져 있는 Demo 사이트로 가서 화면 및 URL을 먼저 살펴봄
* 모두 4개 화면으로 구성되어 있고, 각 화면은 상단의 top과 햄버거 메뉴를 누르면 보여지는 side를 가짐

![Weather Application 분석](/assets/analysis.png)

### 1일차 개발 

1. src 디렉토리 구조를 assets, views, components 3개로 우선 만들고 시작해보기로 함
   * assets : 공통 css, images 등
   * components : 화면을 구성하는 컴포넌트 (Header, Lnb)
   * views : 컴포넌트를 구성하는 화면 (MainPage, LoginPage, AddCityPage DetailsPage)

2. 화면명만 있는 Component를 만들고 reactjs code snippets를 이용해 빠르게 만듦
   * 디렉토리에 js 파일을 만들고, rcc 명령으로 컴포넌트 코드 스니펫을 만든 후 수정하는 방식

![Code Snippet](/assets/codeSnippet.png)

3. index.js에 라우팅 설정
   * App.js를 사용하지 않고 index.js에 바로 입력함. 여기에 하는게 맞나? 하는 부분이 가장 어렵다고 느껴짐
   * 뭐가 더 좋은지는 천천히 기능을 추가해가며 직접 느껴보기로 하고 일단 개발을 계속 진행함

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import * as serviceWorker from './serviceWorker';
import { createBrowserHistory } from "history";
import { Router, Route, Switch } from "react-router-dom";
import LoginPage from './views/LoginPage/LoginPage'
import AddCityPage from './views/AddCityPage/AddCityPage';
import MainPage from './views/MainPage/MainPage';
import DetailsPage from './views/DetailsPage/DetailsPage';

var hist = createBrowserHistory();

ReactDOM.render(
  <Router history={hist}>
    <Switch>
      <Route path="/login" component={LoginPage} />
      <Route path="/addcity" component={AddCityPage} />
      <Route path="/details" component={DetailsPage} />
      <Route path="/" component={MainPage} />
    </Switch>
  </Router>,
  document.getElementById("root")
);

serviceWorker.unregister();
```


4. cmd 창에서 yarn start 명령으로 실행 

```javascript
yarn start
```


5. 결과 및 devtool로 구조 확인

   *  /, /login, /addcity, /details를 옮겨가며 결과를 확인함 
   * Lnb와 Header가 MainPage 밑에 달려있는 부분이 어색하다고 생각됨 --> 2일차 스터디 시간에 개선해볼 예정

![React Application Structure](/assets/structure.png)


6. 해외 블로그에 올라온 원글을 참고해서 각자 최대한 컴포넌트의 정적 구조를 꾸미기

   * HTML 및 Style은 각자 꾸며 오는 걸로하고 1일차 스터디 종료
