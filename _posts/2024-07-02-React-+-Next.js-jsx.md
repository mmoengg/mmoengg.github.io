---
title: (React + Next.js) JSX?
description: JSX?
author: m
date: 2024-07-02 13:20:30 +2000
categories: [Blogging, React]
tags: [react, next.js]
pin: false
math: false
mermaid: false
read: false
---


<br>
예전 방식으로 index.html을 만들면
```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=<device-width>, initial-scale=1.0">
		<title>Document</title>
		<link rel="stylesheet" href="./style.css">
	</head>
	<body>
		<div>hello</div>
	</body>
	<script>
		const a = 1;
		console.log(a);
	</script>
</html>
```
<br>
html을 만들고 js의 영억을 만들고, css 파일을 불러오는 것이 웹프로그래밍의 기본이다.
해당 방법은 페이지가 많아졌을 때 관리라든가 여러 문제가 있다. 그런 부분들을 js 안에서 풀어낼 수 있도록 만든 것이 JSX이다.

<br>
# JSX?
자바스크립트 익스텐션이며, 자바스크립트 안에 HTMl, CSS까지 다 표현할 수 있다.

## pages
pages 아래에 있는 ```.jsx``` 파일은 모두 파일명이 소문자로 작성되어야 한다.
<br>