---
title: (React + Next.js) 파일 구조 + 개발 환경 세팅
description: 파일 구조와 개발 환경을 세팅하자
author: m
date: 2024-07-02 12:20:30 +2000
categories: [Blogging, React]
tags: [react, next.js]
pin: false
math: false
mermaid: false
read: false
---

<br>
# 파일구조
## public
웹 어플리케이션을 구성하는 정적 자원들
파비콘, 아이콘, 이미지 등을 넣고 나중에 배포할 때 그대로 이동시키는 역할
정적 리소스를 배치한다고 알아 두자

## pages
npm run dev를 했을 때 화면이 표시되는 소스가 들어있는 폴더
- _app.js
커스텀 앱 컴포넌트(Custom App Component)
root 컴포넌트이다
컴포넌트 간에 공통적으로 쓰일 코드들이 해당 위치에 정의된다
 _document.js 차후 추가

## styles
어플리케이션과 관계된 스타일 폴더가 들어간다

<br>
# 개발 환경
## Prettier 설치
```
npm i prettier eslint-plugin-prettier eslint-config-prettier -D
```

<br>
## ESLint + Prettier 설정
앞에서 설치한 프리티어를 ESLint 설정 파일에 추가해 주기 위해서 먼저 ESLint 설정 파일 확장자를 JSON에서 JS로 바꾸고 다음과 같이 파일 내용을 변경합니다.
```
// .eslintrc.js
module.exports = {
  extends: ['next/core-web-vitals']
}
```
<br>
다시 JS 파일로 돌아가서 이번엔 다음과 같이 extends, plugins, rules를 추가합니다.
```
module.exports = {
	extends: ['next/core-web-vitals', 'plugin:prettier/recommended'],
	// plugins: ['prettier', 'unused-imports'],
	plugins: ['prettier'],
	rules: {
		// 선언되지 않은 변수 또는 임포트 구문 정리 규칙
		'no-undef': 'error',
		// 'unused-imports/no-unused-imports': 'error',

		// 프리티어 설정
		'prettier/prettier': [
			'error',
			// 아래 규칙들은 개인 선호에 따라 prettier 문법 적용
			// https://prettier.io/docs/en/options.html
			{
				singleQuote: true,
				semi: true,
				useTabs: true,
				tabWidth: 2,
				trailingComma: 'all',
				printWidth: 80,
				bracketSpacing: true,
				arrowParens: 'avoid',
			},
		],
	},
};
```
```module.exports```는 Node.js의 CommonJS 문법이다




<br>