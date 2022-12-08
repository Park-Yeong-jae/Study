### 1) Node.js 설치 및 확인
  - node -v

### 2) npm 버전 확인
  - npm -v

### 3) Vue Cli 설치
  - npm install -g @vue/cli
  
### 4) Vue 버전 확인
  - vue --version
  
### 5) 프로젝트 생성
  - vue create [ 프로젝트 명 ]
  
### 6) 프로젝트로 이동 후 서버 실행
  - cd [ 프로젝트 명 ]
  - npm run serve
  
<hr>

### 1) 페이지 이동 구현 : Vue-router 설치
  - npm i --save vue-router

### 2) src/router 폴더 생성 후 index.js 파일 생성

### 3) src/main.js 파일 vue-router를 사용하도록 아래 소스와 같이 import 시켜줍니다.
  - import { createApp } from 'vue'
    import App from './App.vue'
    import router from './router
    
### 4) src/router의 index.js 파일에서 경로설정
  - Vue.use(VueRouter)
    const routes = [...Dashboard, ...TodoList, ...BoardList, ...Approval, ...Login]

    const router = new VueRouter({
      base: process.env.BASE_URL,
      routes,
      mode: 'history',
      // 화면이 넘어갈때마다 스크롤이 최상단으로 이동
      scrollBehavior(to, from, savedPosition) {
        if (savedPosition) {
          return savedPosition
        }
        return { x: 0, y: 0 }
      },
    })

### 5) src/router/modules 에서 경로설정 할 js 파일 생성 (boardList.js)
  - import { isAuthRequired } from '@/App'

    const resource = [
      {
        path: '/board',
        name: 'BoardList Layout',
        component: () => import('@/views/Main'),
        redirect: '/board/list',
        children: [
          {
            // 게시판 목록
            path: 'list',
            name: 'main',
            component: () => import('@/views/boardList/BoardList'),
            meta: {
              isAuthRequired,
            },
          },
          // 게시판 글 작성
          {
            path: 'create',
            name: 'BoardCreate',
            component: () => import('@/views/boardList/BoardCreate.vue'),
            meta: {
              isAuthRequired,
            },
          },
          // 게시판 글 상세보기
          {
            path: 'detail',
            name: 'BoardDetail',
            component: () => import('@/views/boardList/BoardDetail.vue'),
            meta: {
              isAuthRequired,
            },
          },
        ],
      },
    ]

    export default resource
    
<hr>

### 1) components 사용법
  - src/components/module에 사용할 컴포넌트를 만든다
  - src/views/boardList.vue 에서 import 선언
  - exports default {
    components: {
      Buttons, (import한 이름과 동일하게)
      },
    }
  - 화면에서 <buttons /> 라고 선언하여 사용






### 참고문헌
  - https://onethejay.tistory.com/58
