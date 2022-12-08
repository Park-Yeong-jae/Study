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

### 3) src/main.js 파일 vue-router를 사용하도록 아래 소스로 변경합니다.
  - import { createApp } from 'vue'
    import App from './App.vue'
    import router from './router'

    const app = createApp(App)
    app.use(router).mount('#app')
    
### 4) 






### 참고문헌
  - https://onethejay.tistory.com/58
