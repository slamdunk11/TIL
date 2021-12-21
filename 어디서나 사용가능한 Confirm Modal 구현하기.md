# **어디서나 사용가능한 Confirm Modal 구현하기**

---

- 구현 목적 : window.confirm()창은 커스텀이 되지 않는 아쉬움이 있습니다. 그래서 웹페이지의 디자인적인 통일성을 위해 confirm 기능이 있는 Confirm Modal(확인 모달)을 구현하고자 하였습니다.
- callback함수를 이용하여 true, false 값을 받아와서 true면 액션 실행, false면 액션 취소를 할 수 있도록 구현하였습니다.

## **발생한 어려움과 해결 시도들**

- 1차 어려움 : 확인 모달을 거치면 방 정보가 달라집니다. 예를 들어 방 삭제는 방 정보의 master가 userId가 같아야 실행될 수 있다는 조건이 있습니다. 확인 모달을 거치면 방 정보가 달라지기 때문에 삭제 기능이 실행되지 않습니다.
- 첫 번째 조치 :확인 버튼의 확인, 취소 버튼을 누르면 모달로 부터 true, false를 받아왔습니다. 문제는 확인 모달을 거치면 Id값들이 바뀌어 액션이 실행되지 않으므로 true, false를 리덕스로 올려서 리덕스로부터 이 boolean값을 받아오기로 했습니다.

```
//redux

const initialState = {
  result: false, //확인 버튼 누르면 true
  ...
  msg: "", //확인 모달 msg도 redux를 통해서 가져오기로 합니다.(예시: 정말 삭제하시겠어요?)
};

//DropDown
const result = useSelector((state) => {state.confirm.result})
const msg = useSelector((state) => state.confirm.msg)

```

- 조치 결과 :

result: false ⇒ 확인 누름 ⇒ false && 삭제 실행 X ⇒ 확인모달 닫힘 ⇒ result: true의 순서로 진행되었습니다.

방 정보가 바뀌어버리는 문제는 해결되었으나 행위의 순서가 맞지 않아 결국 확인 후 삭제가 실행되지 않는다는 새로운 문제가 생겼습니다.

- 두 번째 조치 :

첫 번째 조치에서 문제가 되었던 순서를 바꾸기 위해 잠시 고민하였으나, 이후 true로 고정된 result값을 다시 false로 돌려놓는 dispatch 작업을 또 해야해서 다른 곳에서 편하게 사용하기에는 어려운 방식이라고 생각하였습니다.

그래서 result 관련 redux를 걷어내고 Confirm 컴포넌트를 새로 작성하였습니다. 확인 모달에서 true, false를 주고 받지 않아 방 정보가 바뀌는 문제가 생기지 않습니다.

그리고 promise를 사용하여 true, false를 받은 이후 삭제 기능을 실행합니다.

```
//Confirm
...

  // 확인 클릭 시 실행, true를 반환
  const onConfirm = (e) => {
    e.stopPropagation();
    closeConfirm(show);
    resolveCallback(true);
  };

  // window.confirm()의 확인, 취소 기능 구현을 위해
  // Promise 사용하여 true, false 값 받은 이후 액션 실행
  const confirm = (show, msg) => {
    dispatch(__confirm(show, msg));
    return new Promise((res, rej) => {
      resolveCallback = res;
    });
  };
...

//DropDown
...

// Confirm 컴포넌트에서 confirm 가져오기
  // confirm(모달 열고, true, false 값 받기, promise사용해서 true, false 값 받은 뒤에 행동하도록 하는 역할)
  const {confirm} = Confirm();
  const showConfirm = async (show, msg) => {
    const isConfirmed = await confirm(show, msg);

    if(isConfirmed && isMaster) {
      dispatch(__deleteRoom(roomId));
    }else if(isConfirmed && !isMaster){
      dispatch(__exitRoom(roomId));
    }else{
      console.log("취소");
    }
  }
```
