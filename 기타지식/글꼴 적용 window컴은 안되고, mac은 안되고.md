mac은 글꼴이 잘 나오고, window는 글꼴이 제대로 안나와서 괜히 width를 따로 줬던 기억이 있다.
그 때 당시에 window를 썼는데 storybook에는 잘나오고 프론트 결과물에는 글꼴이 안 먹혔다

그 이유는 storybook에는 글꼴을 적용시켜놨고, cra는 글꼴을 적용시켜놓지 않았기 때문이라고 한다...!
글꼴을 추가하는 방법은 아래와 같다!
이런 부분도 잘 몰랐어서 뭐가 문제인지 발견하지 못했다...!
아는 것이 늘어서 기쁘다...!!

```html
// public/index.html
<link
      rel="stylesheet"
      type="text/css"
      href="https://cdn.jsdelivr.net~~~~~"
/>
```
