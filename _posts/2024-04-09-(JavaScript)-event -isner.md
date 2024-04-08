---
title: (JavaScript) addEventListener를 제거해 봅시다.
description: window.addEventListener를 삭제하지 않아서 지속적인 함수의 실행이 반복되었다. 해결책을 찾아 보자.
author: m
date: 2024-04-08 15 16:16:30
categories: [Daily]
tags: [daily]
pin: false
math: false
mermaid: false
read: false
---

모달을 이동할 일이 생겨 `addEventListener`로 모달의 위치를 잡는 작업을 진행했다. 한 번만 실행했을 때는 아무런 문제가 없었는데 여러 번, 여러 모달에 적용하려니 에러가 발생한 것.... `console`에 찍어 보았을 때 처음에 잡혔던 이벤트가 제거되지 않고 중복으로 발생되어 나중에 생긴 이벤트가 무시 당하고 있었던 것.

한 화면에 여러 모달이 이동이 가능해야 했기에 에러를 잡아야만 했다.

## removeEventListener

`addEventListener`를 제거하는 방법은 간단하다. `removeEventListener`를 사용하면 곧장 제거가 된다. 

```console
window.removeEventListener
```
