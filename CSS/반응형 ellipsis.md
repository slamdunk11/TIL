# 반응형 text-overflow: ellipsis
```html
<style>
table{
  width: 100%;  
}
.overflow{
  display: flex;
  flex: 1;
}
.overflow-space{
  flex: 1;
  width: 1px;
}
.overflow-text{
  overflow: hidden; // 해당 element 넘어가는 view는 숨김
  text-overflow: ellipsis;
  white-space: nowrap;
  word-break: break-all;
}
</style>

<table border="1">
  <tr>
    <td>
      <div class="overflow">
      <div class="overflow-space">
      <div class="overflow-text">
        가나다라마바사아자차카타파하하하하하하하하하하하하하하하
        </div>
        </div>
      </div>
    </td>
  </tr>
</table>
```

### 출처 
- https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=psj9102&logNo=221987334475
