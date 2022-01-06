### git clone후 fontawesome 사용 안되었음

- git clone 하면서 npm install했는데 자연스럽게 처리가 안된 듯...

```
npm install --save @fortawesome/react-fontawesome
npm install --save @fortawesome/fontawesome-free
```

- 이거 2개 해주니까 됨
사실 둘 중에 뭐가 부족해서 안되었는 지 모르겠음
위에 있는 거 먼저했는데 안되어서 밑에 있는 것도 했음
내일 또 다른데 git clone할 때 안되면 밑에 있는 거 먼저 해보겠음

- 그리고 index.js에 이 import 추가
```javascript
// index.js
import "@fortawesome/fontawesome-free/js/all.js"
```

- 쓰고 싶은 아이콘 font-awesome에서 찾아서 복사해서 쓴다.
```javascript
<i class="fas fa-coffee"></i>
```

- scss에서 스타일링을 하고 싶다면 class => className으로 사용해서 css처럼 적용한다.


출처: https://velog.io/@winney_77/TIL-35-day-react%EC%97%90%EC%84%9C-font-awesome-%EC%93%B0%EA%B8%B0
