# useEffect

## cleanup

useEffect 함수의 첫번째 매개변수인 setup 함수가 리턴하는 함수이다.<br>

예를 들어 API로부터 데이터를 받아 와서 보여주는 컴포넌트가 있다고 가정하자.<br>
이 컴포넌트가 더 이상 렌더링되지 않는다면, API로부터 데이터를 받아오는 작업도 계속될 이유가 없다.<br>
이런 상황에서 cleanup 함수는 컴포넌트가 언마운트되면 불필요해지는 setup 함수의 작업(API 요청 등)을 멈출 수 있게 해 준다.

⬇️ 예시

```
useEffect(() => {
  // effect
  return () => {
  // cleanup
  };
}, []);
```

cleanup 함수가 호출되는 경우는 두 가지이다.<br>

1. after every re-render with changed dependencies, React will run first run the cleanup function with the old values.
2. after your component is removed from the DOM

\
1번의 예시를 보자.

```
useEffect(() => {
  console.log(count);
  return () => {
    console.log("cleanup: ", count);
  };
}, [count]);
```

- count 변수는 0으로 초기화된다.
- 컴포넌트가 렌더링되고, count가 화면에 0으로 표시된다.
- useEffect가 실행되고, 콘솔에 0이 출력된다.
- 버튼 클릭으로 count가 10이 된다.
- 컴포넌트가 리렌더되고, count가 화면에 10으로 표시된다.
- useEffect의 cleanup 함수가 실행되어 "cleanup: 0"이 콘솔에 출력된다.
- useEffect가 실행되고 콘솔에 10이 출력된다.

참고

- <a href="https://react.dev/reference/react/useEffect#useeffect">Using the Effect Hook - React</a>
- <a href="https://maxrozen.com/demystifying-useeffect-cleanup-function">Demystifying useEffect's clean-up function</a>
