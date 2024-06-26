# Vue.js를 이용한 포트폴리오

Vue.js를 사용하여 포트폴리오 만들기 입니다.

![alt text](/src/assets/img/main.png)

## 구조

프로젝트 디렉토리 구조는 다음과 같습니다.

```
vue-site
├── .vscode
├── dist
├── node_modules
├── public
│   ├── favicon.svg
├── src
│   ├── assets
│   │   ├── img
│   │   ├── scss
│   │   │   ├── fonts.scss
│   │   │   ├── mixin.scss
│   │   │   ├── reset.scss
│   │   │   ├── style.scss
│   │   │   ├── vars.scss
│   ├── components
│   │   ├── ContactSection.vue
│   │   ├── FooterSection.vue
│   │   ├── HeaderSection.vue
│   │   ├── IntroSection.vue
│   │   ├── PortSection.vue
│   │   ├── SiteSection.vue
│   │   ├── SkillSection.vue
│   │   ├── SkipSection.vue
│   ├── constants
│   │   ├── index.js
│   ├── router
│   │   ├── index.js
│   ├── views
│   │   ├── AboutView.vue
│   │   ├── HomeView.vue
├── .eslintrc.cjs
├── .gitignore
├── jsconfig.json
├── vite.config.js
├── package-lock.json
├── package.json
├── README.md
```

## 설치 및 실행 방법

### 최신 버전의 Vue.js, Vue Router, Vite 설치

다음 명령어를 사용하여 최신 버전의 Vue.js, Vue Router, Vite를 설치합니다.

```bash
npm install vue@latest vue-router@latest vite@latest
```

### 추가 의존성 설치

다음 명령어를 사용하여 필요한 패키지를 설치합니다.

```bash
npm install
npm i gsap sass @studio-freight/lenis
```

### 개발 서버 실행

다음 명령어를 사용하여 개발 서버를 실행합니다.

```bash
npm run dev
```

브라우저에서 `http://localhost:3000`을 열어 확인합니다.

## 코드 설명

### `App.vue`

`App.vue` 파일은 프로젝트의 메인 컴포넌트로, Vue Router와 Lenis 스크롤 애니메이션을 설정합니다.

```vue
<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
  <RouterView />
</template>

<script>
import Lenis from 'lenis'

export default {
  mounted: function () {
    this.scrollAnimation()
  },
  methods: {
    scrollAnimation() {
      const lenis = new Lenis({
        duration: 1,
        easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
        direction: 'vertical',
        gestureDirection: 'vertical',
        smooth: true
      })

      function raf(time) {
        lenis.raf(time)
        requestAnimationFrame(raf)
      }

      requestAnimationFrame(raf)

      lenis.on('scroll', (e) => {
        console.log(e)
      })
    }
  }
}
</script>
```

- `RouterView` 컴포넌트: Vue Router를 사용하여 라우팅된 컴포넌트를 렌더링합니다.
- `scrollAnimation` 메서드: Lenis 라이브러리를 사용하여 부드러운 스크롤 애니메이션을 구현합니다. `duration`과 `easing`을 설정하여 스크롤의 속도와 애니메이션 효과를 조정합니다. `requestAnimationFrame`을 통해 지속적으로 스크롤 상태를 업데이트하며, 스크롤 이벤트가 발생할 때마다 콘솔에 이벤트 정보를 출력합니다.

### 섹션 컴포넌트

다양한 섹션 컴포넌트를 `App.vue` 파일에서 불러와 사용합니다.

```vue
<script setup lang="ts">
import HeaderSection from '@/components/HeaderSection.vue'
import SkipSection from '@/components/SkipSection.vue'
import IntroSection from '@/components/IntroSection.vue'
import SkillSection from '@/components/SkillSection.vue'
import SiteSection from '@/components/SiteSection.vue'
import PortSection from '@/components/PortSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import FooterSection from '@/components/FooterSection.vue'
</script>

<template>
  <SkipSection />
  <HeaderSection />
  <main id="main" role="main">
    <IntroSection />
    <SkillSection />
    <SiteSection />
    <PortSection />
    <ContactSection />
  </main>
  <FooterSection />
</template>
```

### `router/index.js`

Vue Router를 사용하여 라우팅을 설정합니다. 두 개의 주요 라우트가 정의되어 있습니다: 홈 페이지와 소개 페이지.

```javascript
import { createRouter, createWebHistory } from 'vue-router'
import HomeView from '../views/HomeView.vue'
import AboutView from '../views/AboutView.vue'

const router = createRouter({
  history: createWebHistory(import.meta.env.BASE_URL),
  routes: [
    {
      path: '/',
      name: 'home',
      component: HomeView
    },
    {
      path: '/about',
      name: 'about',
      component: AboutView
    }
  ]
})

export default router
```

- **라우트 설정**:
  - `HomeView`: 홈 페이지 컴포넌트입니다.
  - `AboutView`: 소개 페이지 컴포넌트입니다.
- `createRouter` 함수: Vue Router 인스턴스를 생성하고, 히스토리 모드를 설정하며, 라우트를 정의합니다.

## Vercel 배포

프로젝트를 Vercel에 배포하기 위해 다음 단계를 따릅니다.

1. [Vercel 계정](https://vercel.com/)을 만듭니다.
2. Vercel 대시보드에서 'New Project' 버튼을 클릭합니다.
3. GitHub, GitLab 또는 Bitbucket 계정을 연결합니다.
4. 배포할 레포지토리를 선택합니다.
5. 프로젝트 설정을 확인하고 'Deploy' 버튼을 클릭합니다.

배포가 완료되면, Vercel은 자동으로 프로젝트의 URL을 제공합니다. 이 URL을 사용하여 웹사이트에 접근할 수 있습니다.

## 사용 기술

- **Vue.js**: 사용자 인터페이스를 구축하기 위한 프레임워크
- **Vue Router**: Vue.js 애플리케이션에서 라우팅을 관리하는 라이브러리
- **SCSS**: CSS 전처리기
- **GSAP**: 애니메이션 라이브러리
- **Lenis**: 스크롤 애니메이션 라이브러리
