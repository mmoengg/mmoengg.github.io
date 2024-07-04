---
title: (React + Next.js) 시작하기
description: Next.js를 시작해 보자
author: m
date: 2024-07-02 11:20:30 +2000
categories: [Blogging, React]
tags: [react, next.js]
pin: false
math: false
mermaid: false
read: false
---

<br>
# Next.js란?
넥스트(Next.js)는 리액트 기반의 웹 애플리케이션 개발을 위한 강력한 프레임워크입니다. 처음에는 주로 서버 사이드 렌더링(SSR) 기능을 제공하는 프레임워크로 알려졌지만, 현재는 다양한 기능을 갖춘 All-in-One 솔루션으로 자리잡았습니다.

리액트 개발자들에게 널리 사용되고 있는 넥스트는 개발 생산성을 높이고, 애플리케이션의 성능과 SEO 최적화를 지원합니다. 또한 정적 페이지 생성, 동적 라우팅, API 라우팅 등의 기능을 제공하여 복잡한 웹 애플리케이션을 쉽게 구축할 수 있게 해줍니다.

<br>
## Next.js 주요 특징
넥스트(Next.js)는 리액트 개발에 있어 다양한 편의 기능을 제공하는 강력한 프레임워크입니다. 기존의 리액트 프로젝트 생성 도구들에 비해 다음과 같은 특징을 가지고 있습니다:

1. 라우팅: 별도의 리액트 라우터(React Router) 설정 없이도 <b>파일 기반 라우팅 시스템</b>을 제공하여 서버 컴포넌트, 레이아웃, 에러 처리, 로딩 상태 관리 등을 편리하게 다룰 수 있습니다.
2. 렌더링: 클라이언트 사이드 렌더링과 서버 사이드 렌더링을 모두 지원하여 다양한 요구사항을 충족시킬 수 있습니다.
3. 데이터 호출: 브라우저의 fetch API를 확장하여 데이터 캐싱, 유효성 검사 등의 기능을 제공합니다.
4. 스타일링: CSS 모듈, CSS in JS, Tailwind 등 다양한 스타일링 방식을 바로 구성할 수 있습니다.
5. 성능 최적화: 이미지, 폰트, 스크립트 등의 리소스를 최적화하여 웹 성능을 개선합니다.
6. 타입스크립트: 이전 버전보다 타입스크립트 지원이 강화되어 보다 안정적인 개발이 가능합니다.

<br>
> 라우팅(Routing)이란 페이지를 이동하는 동작을 의미합니다.

<br>
## Next.js 프로젝트 생성
다음과 같은 명령어로 새로운 Next.js 프로젝트를 생성할 수 있습니다:
<br>
```
npx create-next-app@latest
```

<br>
이 명령어를 실행하면 Next.js 프로젝트를 설정하는 과정이 시작됩니다. 이 과정에서 다음과 같은 선택 사항들을 결정할 수 있습니다:
<br>
```
✔ What is your project named? … learn-next
✔ Would you like to use TypeScript? … No / Yes
✔ Would you like to use ESLint? … No / Yes
✔ Would you like to use Tailwind CSS? … No / Yes
✔ Would you like to use `src/` directory? … No / Yes
✔ Would you like to use App Router? (recommended) … No / Yes
✔ Would you like to customize the default import alias (@/*)? … No / Yes
```

<br>