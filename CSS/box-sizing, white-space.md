# box-sizing : content-box
- 요소의 width(너비)를 100px로 설정하면 콘텐츠 영역이 100px 너비를 가지고, 테두리와 안쪽 여백(padding)은 이에 더해짐
<img width="768" alt="image" src="https://user-images.githubusercontent.com/61729276/160628154-79a56e8d-f893-4842-b934-13ffafc18a45.png">


# box-sizing : border-box
- 테두리와 안쪽 여백의 크기도 요소의 크기로 고려함...width를 100px로 설정하고 테두리와 안쪽 여백을 추가하면 콘텐츠 영역이 줄어들어 총 너비 100px을 유지한다
- <img width="804" alt="image" src="https://user-images.githubusercontent.com/61729276/160628733-075bd0fd-0bfa-43b3-a4d2-9caba769d5b2.png">

# white-space : nowrap
- 연속 공백을 하나로 합침....줄바꿈x

* 반응형 할 때 버튼이 막 모양이 우그러지면 box-sizng: content-box, white-space: nowrap 함께 쓴다!
