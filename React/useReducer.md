# useReducer

## reducer

<p>
컴포넌트가 커지면서, 그 안에 있는 state logic이 점점 복잡해질 수 있다.<br>
그 복잡도를 줄이기 위해, reducer라는 컴포넌트 밖에 있는 하나의 함수에 모든 state logic을 옮길 수 있다.<br>
다시 말해, useReducer는 useState 외에 상태 관리를 할 수 있는 또다른 방법이다.<br>
</p>
<br>

> How to migrate from useState to useReducer

1. Move from setting state to dispatching actions.
2. Write a reducer function.
3. Use the reducer from your component.

<br>

### Step 1

<p>
이벤트 핸들러로부터 액션을 dispatch함으로써 유저가 방금 무엇을 했는지를 특정한다.<br>

예시 ⬇️

```
function handleChangeTask(task) {
    dispatch({
        type: "changed",
        task: task,
    })
}
```

이렇게 `dispatch`에 넘겨주는 객체를 action이라고 한다.  
그리고 `dispatch`는 액션을 발생시키는 함수라고 이해하면 됨

</p>
<br>

### Step 2

<p>
state logic을 포함할 reducer 함수를 만든다.<br>
2개의 매개변수가 필요하다. (현재 상태, action 객체)<br>
reducer 함수로부터 리턴되는 것으로 state가 설정될 것이다.<br>
여기서 `action`은 업데이트를 위한 정보를 가지고 있음

예시 ⬇️

```
function reducer(state, action) {
    if (action.type === "added") {
        return [
            ...tasks, {
                id: action.id,
                text: action.text,
                done: false
            },
        ];
    } else if (action.type === "changed) {
        // return ...
    }
}
```

예시에서는 if문을 썼지만, 보통 switch문을 써 주는 것이 관행이다.

</p>
<br>

### Step 3

<p>
컴포넌트 내에 reducer를 써 준다.

```
const [tasks, dispatch] = useReducer(reducer, initialState);
```

원한다면 reducer를 다른 파일로 분리할 수도 있다.

</p>
<br>

### Tips

- 리듀서는 컴포넌트 밖에 있는 것에 영향을 주는 작업을 수행해서는 안 된다. (요청 보내기, 타임아웃 등)
- 하나의 액션은 하나의 유저 인터랙션을 나타내야 한다.

참고

- <a href="https://react.dev/learn/extracting-state-logic-into-a-reducer">Extracting State Logic into a Reducer - React</a>
