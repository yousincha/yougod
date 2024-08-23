---
layout: post
title: 온열질환 API
categories: Heat_Illness
tags: [JavaScript, JSON, MySql, axios, socket.io]
---

## 온열질환 API

이 프로젝트는 온열질환 예방 시스템(Heat Illness Prevention System)의 웹 애플리케이션 서버로, Express.js와 같은 Node.js 프레임워크를 기반으로 구축되었습니다. 다양한 라우트를 통해 관리자의 시스템 관리 및 사용자의 건강 데이터 처리 기능을 제공합니다.

## 소개

온열질환 API는 온열질환 예방을 위해 사용자 및 관리자 기능을 제공합니다. 이 API는 사용자 로그인, 회원 가입, 건강 정보 관리, 긴급 상황 보고 등의 기능을 포함하여, 온열질환과 관련된 데이터를 효율적으로 관리할 수 있도록 설계되었습니다. 이 시스템은 관리자와 사용자 모두를 위한 다양한 라우트를 제공하여 웹 애플리케이션의 핵심 백엔드 서비스를 신속하고 효율적으로 구축할 수 있도록 지원합니다.

## 주요 기능

- **사용자 인증 및 관리**: 사용자 로그인, 회원 가입, 비밀번호 찾기 등 사용자의 인증 및 계정 관리를 지원합니다.
- **사용자 정보 관리**: 사용자 개인 정보 및 기기 정보를 등록, 조회, 수정할 수 있습니다.
- **보호자 관리**: 보호자를 등록, 삭제, 조회하는 기능을 제공합니다.
- **건강 데이터 관리**: 사용자 건강 데이터를 보고하고, 긴급 상황을 보고할 수 있습니다.
- **날씨 데이터 연동**: 사용자의 현재 위치를 기반으로 자외선 지수, 미세먼지 농도, 날씨 예보등을 조회 하고, 농도에 따라 적절한 경고 메시지와 이미지를 표시합니다.
- **관리자 기능**: 관리자 로그인, 로그아웃, 사용자 및 팀 정보 조회, 삭제, 긴급 치료 관리, SMS 전송 등을 할 수 있습니다.
- **긴급 상황 보고**: 사용자로부터 긴급 상황을 보고받아 관리자가 적절히 대처할 수 있도록 합니다.
- **실시간 통신**: Socket.io를 이용하여 실시간 통신을 지원합니다.

## API 엔드포인트

- **사용자 인증 및 관리**
  - POST /app_process/login: 사용자가 로그인할 수 있도록 지원합니다.
  - POST /app_process/auth_access: 사용자 권한 확인 및 인증 처리를 합니다.
  - POST /app_process/join_member: 새로운 사용자를 등록합니다.
  - POST /app_process/id_search: 사용자가 아이디를 찾을 수 있도록 지원합니다.
  - POST /app_process/pw_search: 사용자가 비밀번호를 찾을 수 있도록 지원합니다.
  - POST /app_process/pw_change: 사용자가 비밀번호를 변경할 수 있도록 합니다.
  - POST /app_process/id_check: 회원 가입 시 아이디 중복 여부를 확인합니다.
  - POST /app_process/email_check: 회원 가입 시 이메일 중복 여부를 확인합니다.
  - POST /app_process/assign_code_check: 사용자 등록 코드의 유효성을 확인합니다.

<br>

- **사용자 정보 관리**
  - POST /app_process/user_info_regi: 사용자의 상세 정보를 등록합니다.
  - POST /app_process/user_info_req: 사용자 정보를 조회합니다.
  - POST /app_process/user_info_update: 사용자 정보를 업데이트합니다.
  - POST /app_process/dev_regi: 사용자의 기기를 시스템에 등록합니다.

<br>

- **보호자 관리**
  - POST /app_process/protector_regi: 사용자가 보호자를 등록합니다.
  - POST /app_process/protector_del: 사용자가 등록된 보호자를 삭제합니다.
  - POST /app_process/protector_req: 보호자 정보를 조회합니다.

<br>

- **건강 데이터 관리**
  - POST /app_process/vital_report: 사용자가 건강 정보를 서버에 제출합니다.
  - POST /app_process/emergency_report: 긴급 상황 발생 시 서버에 보고합니다.

<br>

- **관리자 기능**
  - GET /web_process/manager_login: 관리자 로그인 페이지를 제공합니다.
  - POST /web_process/manager_login: 관리자가 로그인할 수 있도록 지원합니다.
  - POST /web_process/manager_logout: 관리자가 로그아웃할 수 있도록 합니다.
  - POST /web_process/manager_team_search: 관리자가 사용자 팀을 검색합니다.
  - POST /web_process/manager_user_delete: 관리자가 특정 사용자를 삭제할 수 있습니다.
  - POST /web_process/card/manager_user_delete: 카드에 등록된 사용자를 삭제합니다.
  - POST /web_process/manager_user_search: 관리자가 사용자 정보를 검색합니다.
  - POST /web_process/manager_send_sms: 보호자에게 긴급 상황을 알리는 SMS를 전송합니다.
  - POST /web_process/manager_emg_treatment: 긴급 치료 상황을 관리합니다.
  - POST /users/list, GET /users/list: 관리자가 사용자 리스트를 조회합니다.
  - POST /users/cardlist, GET /users/cardlist: 관리자가 사용자 카드 리스트를 조회합니다.
  - POST /users/detail: 관리자가 특정 사용자의 세부 정보를 조회합니다.

## 설치 방법

이 프로젝트는 Node.js 기반의 웹 애플리케이션 서버로, 다양한 라이브러리를 사용하여 개발되었습니다. 아래의 단계를 따라 설치 및 실행할 수 있습니다.

### 필수 조건

- [Node.js 18.x](https://nodejs.org/en/)
  이상이 설치되어 있어야 합니다.
- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) 또는[Yarn](https://yarnpkg.com/getting-started/install)
  이 설치되어 있어야 합니다.
- MySQL 데이터베이스가 설치되어 있고, 접근 가능한 상태여야 합니다.

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

# 환경 변수 설정

프로젝트 루트 디렉토리에 .env 파일을 생성하고, 필요한 환경 변수를 설정합니다.

```bash
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=yourdatabase
JWT_SECRET=yourjwtsecret

```

# 애플리케이션 실행

애플리케이션을 실행하려면, 다음 명령어를 사용합니다.

```bash
npm start
```

이 명령어는 nodemon을 사용하여 애플리케이션을 자동으로 재시작하면서 실행합니다.

# 테스트 실행

프로젝트의 테스트를 실행하려면, 다음 명령어를 사용합니다.

```bash
npm run lint
```

이 명령어는 모든 단위 테스트를 실행합니다.

# 추가 설정

- app.js 또는 index.js에서 애플리케이션 설정을 조정할 수 있습니다.
- MySQL 연결 설정은 config 디렉토리에서 관리할 수 있습니다.

---
