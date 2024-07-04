---
title: Next.js 외부 이미지 가져올 때 에러
description: 
author: m
date: 2024-07-04 17:20:30 +2000
categories: [Trouble shooting]
tags: [react, next.js]
pin: false
math: false
mermaid: false
read: false
---

<br>
## 😢 문제 발생
![image](https://github.com/mmoengg/whiary/assets/115635503/b8015f7d-27ef-481e-a985-9c7c9ef26305)
github에서 이미지 링크를 추출하고, 해당 링크를 MongoDB의 데이터베이스에 넣어 둔 상태이다.
이미지의 최적화를 위해 Next.js가 지원하는 Image 컴포넌트를 사용 중인데, github 링크 자체에 접근이 안 되는 듯하다.

### 원인 파악
- Image 컴포넌트의 props인 src는 외부의 이미지를 사용할 경우 악의적인 유저로부터 어플리케이션을 보호하기 위해 해당 에러를 띄운다.
- next.config.js에서 허용할 특정 외부 도메인을 remotePatterns로 추가해 주어야 한다.
- remotePatterns 외에 domains를 사용해도 된다.

<br>
<br>
## 💡 해결 방안
### 1. next.config.js - remotePatterns
```
// before

/** @type {import('next').NextConfig} */
const nextConfig = {
	reactStrictMode: true,
};

export default nextConfig;
```

```
// after

/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: 'github.com',
      },
    ],
  }
};

module.exports = nextConfig;
```

### 1-2. next.config.js - domains
```
// after

/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  images: {
    domains: ['github.com'],
  }
};

module.exports = nextConfig;
```

<br>
<br>
## ⌨️ 결과
![image](https://github.com/mmoengg/whiary/assets/115635503/542dbd83-8313-4488-a945-3befe088403c)
화면에 에러 없이 정상적으로 이미지가 불러와지고 있다. 확실히 바닐라 JS를 쓰다가 프레임워크를 사용하게 되니 새로운 에러가 많이 보인다. 알아서 최적화 해 주느라 발생하는 에러를 만나기도 하는구나 싶다....

<br>
<br>
## 📖 래퍼런스
> [Next.js 공식 문서 / <Image> Components](https://nextjs.org/docs/pages/api-reference/components/image)
{: .prompt-tip }
<br>
<br>