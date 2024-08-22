---
layout: post
title: 홈페이지 서버 API
categories: HOMEPAGE
tags: [Node.js, Express, MongoDB, JWT]
---

## 홈페이지 서버 API

이 API는 Node.js와 Express를 기반으로 하여 강력하고 유연한 서버 사이드 기능을 제공합니다. MongoDB를 사용하여 데이터를 관리하고, JWT를 활용하여 사용자 인증을 처리합니다.

## 소개

홈페이지 서버 API는 다양한 기능을 제공하여 개발자들이 빠르게 웹 애플리케이션의 백엔드 시스템을 구축할 수 있도록 돕습니다. 이 API는 사용자 인증, 파일 업로드, 데이터 관리 등의 기능을 포함하여 현대적인 웹 애플리케이션을 지원합니다.

## 주요 기능

- **고객 정보 관리**: 고객 정보를 조회하고 수정할 수 있는 페이지입니다.
- **뉴스 관리**: 뉴스 정보를 조회하고 수정할 수 있는 페이지입니다.
- **연혁 관리**: 연혁 정보를 조회, 수정, 추가할 수 있는 페이지입니다.
- **상태 관리**: Redux를 사용하여 애플리케이션의 상태를 중앙에서 관리하고, 컴포넌트 간 상태 공유를 쉽게 처리합니다.
- **파일 관리**: Dropzone 컴포넌트를 활용하여 사용자에게 파일 업로드 기능을 제공합니다. 업로드된 이미지는 서버에 저장되며, 사용자는 이를 관리할 수 있습니다.
- **인증 관리**: 인증 상태에 따라 접근 가능한 라우트를 제어합니다. 인증되지 않은 사용자는 로그인 페이지로 리디렉션되며, 인증된 사용자는 홈 페이지로 이동합니다.

## API 엔드포인트

- **고객 API**
  - GET /customer: 고객 목록을 가져옵니다.
  - DELETE /customer/{customerId}: 특정 고객을 삭제합니다.

<br>

- **뉴스 API**
  - GET /news: 뉴스 목록을 가져옵니다. (예: 최신 뉴스)
  - GET /news/{newsId}?type=single: 특정 뉴스의 상세 정보를 가져옵니다.
  - PUT /news/{newsId}: 특정 뉴스의 정보를 업데이트합니다.
  - DELETE /news/{newsId}: 특정 뉴스를 삭제합니다.

<br>

- **연혁 API**
  - GET /history: 연혁 목록을 가져옵니다.
  - POST /history: 새로운 연혁을 추가합니다.
  - PUT /history/{historyId}: 특정 연혁의 정보를 업데이트합니다.
  - DELETE /history/{historyId}: 특정 연혁을 삭제합니다.

<br>

- **이미지 API**
  - GET /image/getimages: 이미지 목록을 가져옵니다.
  - PUT /image/updateimage: 이미지를 업데이트합니다.

## 설치 방법

이 프로젝트는 Node.js를 기반으로 하며, Express와 MongoDB를 사용합니다. 아래의 단계를 따라 설치 및 실행할 수 있습니다.

### 필수 조건

- [Node.js 18.x](https://nodejs.org/en/)
  이상이 설치되어 있어야 합니다.
- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) 또는[Yarn](https://yarnpkg.com/getting-started/install)
  이 설치되어 있어야 합니다.

### 프로젝트 클론

먼저, 이 프로젝트를 클론합니다:

```bash
git clone <프로젝트 레포지토리 URL>
cd <프로젝트 디렉토리>
```

# 종속성 설치

프로젝트 디렉토리에서 Gradle을 사용하여 필요한 종속성을 설치합니다.

```bash
npm install
```

# 애플리케이션 실행

애플리케이션을 실행하려면, 다음 명령어를 사용합니다.

```bash
npm run dev
```

이 명령어는 Spring Boot 애플리케이션을 실행합니다.

# 테스트 실행

프로젝트의 테스트를 실행하려면, 다음 명령어를 사용합니다.

```bash
npm run lint
```

이 명령어는 모든 단위 테스트를 실행합니다.

---

[홈페이지 확인하러 가기](http://www.vlv.co.kr/)
<br><br><br><br><br>

---
