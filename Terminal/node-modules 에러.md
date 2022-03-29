# node-modules 에러
git pull을 하고 나서 이상한 에러가 난 적이 있다!
fontSize, color...등등 온갖 곳에서 에러가 났었는데
문제는 node-modules이었다!
늘 도움주시는 리드님께서 도와주셨다...!😭👍
```
rm yarn.lock
rm -rf node_modules
// 이렇게 지워주고
yarn install (줄여서 yarn)
// 새로 설치해주면 된다!
```
