---
title: Next.js + Vercel + MongoDB 연동 및 배포 후 504 error
description: 
author: m
date: 2024-07-04 13:20:30 +2000
categories: [Trouble shooting]
tags: [react, next.js, next.js, vercel]
pin: false
math: false
mermaid: false
read: false
---

<br>
## 😢 문제 발생
![제목 없음](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/d914ad31-f8e1-47be-b1ac-cd39e44b6555)
Next.js에 MongoDB 연동 후 Vercel에 배포하고 환경변수 셋팅까지 마친 상태에서, 데이터베이스 접근 시 서버 액션 호출에서 에러가 지속적으로 발생했다.

### 원인 파악
- Vercel에서 서버 액션 함수를 사용할 때 Serverless 환경에서 실행된다.
- Serverless 환경에서는 각 함수 호출마다 동적으로 IP 주소가 할당된다.

<br>
<br>
## 💡 해결 방안
### 1. Vercel Projects에서 Integrations 접근
![image](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/bbafa1a5-3f71-49b1-ae0e-3bdf52a2b3af)

### 2. Integrations에서 MongoDB Atlas 선택
![image](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/fbdc97ec-69bd-4947-841a-65fda1747830)

### 3. Add Integration 선택
![image](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/b2bfccbc-6569-4a08-8b04-52f129c03082)

### 3-1. 계정 선택 후 프로젝트 선택
![image](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/3fe2b2bd-5b3f-451e-8e2e-ed64ba5a4ca1)

### 4. MongoDB 로그인 후 데이터베이스 선택

<br>
<br>
## ⌨️ 결과
![image](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/0813f5fa-387a-42fa-a1d3-73312d7cb2fa)
![image](https://github.com/mmoengg/mmoengg.github.io/assets/115635503/9c5dee8a-cb99-4c2d-82af-835b090d6a3d)
배포된 Vercel 화면에서도 MongoDB에 접근하여 데이터를 잘 가져오고 있다.

<br>
<br>
## 📖 래퍼런스
> [MongoDB 공식 문서 / Vercel과 통합](https://www.mongodb.com/docs/atlas/reference/partner-integrations/vercel/)
{: .prompt-tip }
<br>
<br>