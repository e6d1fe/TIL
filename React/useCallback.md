# useCallback

useCallback은 컴포넌트가 리렌더될 때 내부에 작성된 함수를 재생성하지 않도록 메모이제이션하는 리액트 훅이다.

```
const memoizedFunc = useCallback(콜백함수, 의존성배열);
```

useCallback의 첫번째 인수로 전달한 콜백함수에서 state 변수에 접근하는 경우 문제가 발생할 수 있다.<br>
그렇게 하면 콜백 함수가 컴포넌트의 마운트 시점 이후에는 다시 생성되지 않아서 state의 초기값만 반환한 채 state의 변화를 추적하지 못하기 때문이다.<br>
이를 해결하려면 setState의 인수로 콜백 함수를 전달하면 된다.

```
const onCreate = useCallback(() => {
    setState((state) => setState[newItem, ...state]);
}, []);
```

이렇게 setState에서 콜백 함수를 전달하면 함수형 업데이트를 사용할 수 있는데, 이 함수는 항상 최신 state 값을 매개변수로 저장한다.<br>
따라서 useCallback을 사용하며 setState로 최신 state 값을 추적하려면 이렇게 함수형 업데이트 기능을 사용해야 한다.<br>
useReducer가 반환하는 함수 dispatch가 호출하는 reducer 함수는 항상 최신 state를 인수로 받으므로, 이 때는 함수형 업데이트를 사용하지 않아도 된다.
<br>

참고

- 한 입 크기로 잘라 먹는 리액트 - 이정환
