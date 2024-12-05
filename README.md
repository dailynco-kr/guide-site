# 가이드사이트

## 초기세팅
**논의 후 한명이 설치 한 후 develop 브랜치로 push 하여 pull 받기**

1. React 프로젝트 생성<br>
`npx create-react-app your-project-name` <br>
혹시**vite** 를 사용할것이라면  <br>
`npm create vite@latest my-vite-app`<br>
`cd my-vite-app`<br>
`npm install`<br>
`npm run dev`  <br>
    ```
    Vite를 사용하는 이유?

    - 빠른 개발 환경이 필요할 때
    - SPA 프레임워크(React, Vue 등)로 작업할 때
    - 프로젝트 초기 설정에 시간을 절약하고 싶을 때
    - 최신 브라우저 기능을 우선적으로 활용하고 싶을 때
    ```

2. React Router 설치 `npm install react-router-dom`

3. style 방식 
  - scss : `npm install sass` <br>
  - (다른 방법 제안주셔도 됩니다!)

4. ESLint 및 Prettier
  - `npm install eslint --save-dev` <br>
    `npx eslint --init`
  - `npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier`
    ```js
    //.eslintrc.js 파일에 삽입
    module.exports = {
      extends: [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:prettier/recommended"
      ],
      rules: {
        "prettier/prettier": ["error", { "endOfLine": "auto" }]
      }
    };

    ```


## code 컨벤션

- 반복되는 작업 하드코딩 하지 않기 ⇒ constant 파일 분리
- 컴포넌트로 분리된 파일은 PascalCase으로 작성합니다.
- 컴포넌트가 아닌 파일은 camelCase로 작성합니다.
- 함수명, 변수명은 camelCase로 작성합니다.
- 만약 변수에 할당되는 값이 boolean인 경우에는 is를 접두사로 붙입니다.
- 상수는 대문자로만 작성합니다.
- 문자열을 처리할 때는 쌍따옴표를 사용하도록 합니다.
- 가독성을 위해 한 줄에 하나의 문장만 작성합니다.
- 주석은 설명하려는 구문에 맞춰 들여쓰기 합니다.
- 연산자 사이에는 공백을 추가하여 가독성을 높입니다.
- 콤마 다음에 값이 올 경우 공백을 추가하여 가독성을 높입니다.

## Git branch 전략

참고 : [https://velog.io/@junsu1222/깃-컨벤션-및-깃-브랜치-전략](https://velog.io/@junsu1222/%EA%B9%83-%EC%BB%A8%EB%B2%A4%EC%85%98-%EB%B0%8F-%EA%B9%83-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EC%A0%84%EB%9E%B5)

### 공통 
- main : 출시 가능한 코드를 모아두는 브랜치
- develop
    - 다음 버전 개발을 위한 코드를 모아두는 브랜치
    - main 에서 브랜치를 처음 생성하고 개발이 완료되면 main으로 머지
 
### 방법 1. 
- feature
    - 새로운 기능을 개발하기 위한 브랜치
    - develop 에서 브랜치를 생성하고, 기능 개발이 완료되면 develop으로 머지
    
    ```bash
    git checkout -b feature/기능명
    ```
    
- release
    - 소프트웨어 배포를 준비하기 위한 브랜치
    - Develop 브랜치에서 생성하며, 소소한 데이터를 수정 및 배포전 사소한 버그를 수정하기 위해 사용
    - 배포 준비가 완료되었다면 Main 과 Develop 브랜치에 둘 다 머지 함
- hotfix
    - 이미 배포된 버전에 문제가 발생했다면, Hotfix 브랜치를 사용하여 문제 해결
    - Main 브랜치에서 생성 → 문제 해결이 완료되면 Main과 Develop 브랜치에 둘 다 머지


### 방법 2.
 - 각자 이름으로 된 브랜치 생성 하여 작업
    ```bash
    git checkout -b 이름/기능명
    ```
### 방법 3. 
 - 1번 2번 방식 합치기
    ```bash
    git checkout -b feature/이름/기능명
    ```

## commit 컨벤션

```jsx
git commit -m "feat: 내용"
```

| 타입 | 설명 |
| --- | --- |
| Docs | 문서 작업 |
| Feat | 새로운 기능 구현 |
| Design | UI/스타일 파일 추가/수정 |
| Fix | 버그 수정 |
| Refactor | 코드 리팩토링을 했을 때 |
| Move | 파일 | 코드의 이동 |
| Rename | 파일명 | 디렉토리명 변경 |
| Remove | 사용하지 않는 코드 | 파일 삭제 |
| Chore | 잡일.. 주석 추가/제거/수정 등 |
| Add | npm 등 설치 실행 관련 |
| HOTFIX | 치명적인 버그 수정 |
