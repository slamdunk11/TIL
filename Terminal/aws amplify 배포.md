# AWS amplify
- amplify는 git과 연동되어 git에 올리기만 해도 배포가 완료된다!
- 아주 편리하다!

# AWS amplify 배포
- 위에서 말했 듯 git에 올리기만해도 배포가 되는 것이라서
- git의 main 브랜치에 develop 브랜치를 merge 해주는 과정이다!

### 1. merge develop into main 하는 법
--> git checkout main // main으로 브랜치 바꾸고<br/>
-->git pull<br/>
-->git merge develop // develop 브랜치를 main에 merge!

### 2. add tag(version) to the commit 하는 법
(2~3번 fork 프로그램을 이용하면 편하다, fork는 homebrew를 통해 vscode 터미널에서 설치 가능!<br/>
`fork`를 킬 때는 vscode에서 fork라고 칠 것, 안 그러면 push할 때 권한 없다고 husky 에러 나옴)<br/>
`fork` 에서 main 브랜치에 new tag <br/>
=> 배포할 버전(package.js에서 확인, 혹은 github에 최근 커밋으로 확인)<br/>
=> 하고 나서 push할 때 all tags!

### 3. push main with the tag
