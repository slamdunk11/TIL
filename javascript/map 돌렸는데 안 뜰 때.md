# map
```javascript
...
{array.map((item, index)=>{
 // 이렇게 중괄호를 쓰면 return을 꼭 써줘야한다...!!!
 return(<div>...</div>)
})

{array.map((item, index)=>(
// 그냥 소괄호를 쓰면 return 표기 필요없다!
<div>...</div>
))}
```

> 부끄럽게도 이걸 발견을 못해서 시간이 초큼 걸렸다. 위의 방식대로 사용하지 않으면 map 결과물이 아예 화면에 뜨지 않았다.
> 이런 기본적인 문법을 잘 숙지하고 공부해야겠다. 오늘도 조금 더 배웠다!
