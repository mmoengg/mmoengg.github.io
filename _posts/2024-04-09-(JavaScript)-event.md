---
title: (JavaScript) addEventListener를 제거해 봅시다.
description: window.addEventListener를 삭제하지 않아서 지속적인 함수의 실행이 반복되었다. 해결책을 찾아 보자.
author: m
date: 2024-04-09 12:40:30 +2000
categories: [Today I Learned]
tags: [javascript, html]
pin: false
math: false
mermaid: false
read: false
---

<br>
## 😢 이벤트 리스너가 필요해

모달을 이동할 일이 생겨 `addEventListener`로 모달의 위치를 잡는 작업을 진행했다. 한 번만 실행했을 때는 아무런 문제가 없었는데 여러 번, 여러 모달에 적용하려니 에러가 발생한 것.... <br>
 `console`에 찍어 보았을 때 처음에 잡혔던 이벤트가 제거되지 않고 중복으로 발생되어 나중에 생긴 이벤트가 무시 당하고 있었던 것.

한 화면에 여러 모달이 이동이 가능해야 했기에 에러를 잡아야만 했다.

<br>
## 🙏 removeEventListener

`addEventListener`를 제거하는 방법은 간단하다. `removeEventListener`를 사용하면 곧장 제거가 된다. 

```console
window.removeEventListener(type, listener)
```

<br>
## 😅 익명 함수는 돌아가

그러나... 내 작업엔 적용되지 않았다. 왜냐면, `removeEventListener`는 익명 함수를 제거할 수 없기 때문이다. ^^... add와 완전 동일하게 적어 주어야 삭제가 가능하다.
파라미터로 전달해야 하는 요소가 있어서 익명 함수를 전달할 수밖에 없는 상황이라 당황했다.
<br>
<br>
전역 변수를 하나 선언하고, 함수가 실행되면 변수에 값을 담아 넘기는 형태로 전달해보자.

```console
let isPress = false, // 드래그 상태 표시
	prevPosX = 0, // 이전 마우스 좌표 X
	prevPosY = 0, // 이전 마우스 좌표 Y
	startDrg, // 드래그 시작 함수
	moveEventListener; // 이벤트 리스너 함수
```
```console
function draggable(el) {
	startDrg = function (e) {
		startDragging(el, e);
	};
	el.addEventListener('mousedown', startDrg); // 드래그 시작 시
	el.addEventListener('mouseup', endDragging); // 드래그 종료 시

	moveEventListener = function (e) {
		moveElement(el, e);
	};
	window.addEventListener('mousemove', moveEventListener); // 드래그 중
}
```

위와 같이 작성하면 매개변수도 넘길 수 있고, 이벤트 리스너를 제거할 수도 있다!

<br>
## 🫡 이래서였구나

이벤트 리스너를 함부로 사용하면 안 된다는 것을 알았다. 로그의 지옥을 맛볼 뻔했다. (아니 봤음.)
또, 삭제 시 이벤트 리스너를 어떻게 작성해야 하는지 이번 기회에 제대로 알게 된 것 같다.

<br>