# github...알다가도 모르겠다
내가 React 공부를 하려고 새롭게 프로젝트를 만들었다.
한 폴더 안에 폴더가 여러개 있었고 나는 그 중 하나의 폴더만 github에 올리고 싶었다.
그런데 내가 그걸 까먹고 여러 폴더가 들어있는 한 폴더를 깃헙에 다 올리고 말았다.

나는 침착하게 내가 원하는 폴더로 들어가서
```
git checkout -b 브랜치명
```
을 시전했다. 
새 브랜치를 만들어서 내가 원하는 폴더를 올리고, 기존 브랜치는 삭제하면 된다고 생각했다.
그리고 나서 새 브랜치를 원격 repository에 push해야하니까
```
git push --set-upstream origin 브랜치명
```
을 했다.

그런데...!
![image](https://user-images.githubusercontent.com/61729276/148387028-9f089b59-30ad-433d-9bbc-f0ecb6bbdf01.png)

레포지토리가 2개 되었다. React_ToDoList와 habit-tracker.
기존에 내가 만들어둔 레포지토리가 React_ToDoList이고 habit-tracker는 올리려고 했던 폴더 이름이다.
이게 레포지토리 이름이 되어버렸다. 몹시 당황스럽다...set-upstream 어쩌구는 원격레포지토리와 새로 만든 브랜치를 연결해주는 그런 친구 아니었나...?

그럼 내 생각에는 React_ToDoList에 habit_tracker라는 브랜치가 만들어져야 맞는데
habit-tracker 레포지토리가 만들어지고 master와 habit_tracker라는 브랜치가 그 안에 생겼다.

확인해보니 내가 React_ToDoList에 올린 '초기설정'이라는 커밋이 master 브랜치에 그대로 있다.
뭔가 연결되어서 이렇게 넘어온 거 같긴한데 약간 당황스럽다.
이 habit_tracker에서 pr을 했을 때 React_ToDoList에 변화가 있는 지 확인해보고 이어서 작성하겠다. 
