# context

context를 사용하는 이유: props drilling 문제를 해결하기 위해서

<br>

### props drilling

이 문제는 리액트 컴포넌트 계층 구조에서 props를 전달할 때 발생한다.<br>
props는 언제나 부모에서 자식으로 단방향으로 전달되기 때문에, 컴포넌트 트리에서 2단계 이상 떨어져 있는 컴포넌트에 직접 데이터를 전달하는 것이 불가능하다.<br>
이런 상황에서 props를 전달하려면 아래 계층으로 계속 전달을 해 줘야 하는데, 이렇게 props drilling을 하면 컴포넌트 사이의 데이터 교환 구조를 파악하기가 힘들다.<br>
context를 이용하면 컴포넌트 트리 전역에 데이터를 공급할 수 있게 되어 이 문제를 해결할 수 있다.<br>

React.createContext를 이용하면 새로운 context를 만들 수 있다.<br>
예시 ⬇️

```
const MyContext = React.createContext(defaultValue);
```

<br>

### useContext

특정 context가 공급하는 데이터를 불러오는 리액트 훅이다.<br>
예시 ⬇️

```
function ExampleComponent() {
    const data = useContext(MyContext);
}
```

⭐️ context는 반드시 컴포넌트 밖에서 생성해야 한다!

<br>

### context 사용하기

1. context 생성하고 export하기
2. Provider를 컴포넌트에 배치해 데이터 공급 설정하기
3. 공급할 값을 Provider 컴포넌트에 전달하기
4. context가 필요한 컴포넌트에서 useContext를 사용해 받아오기

<br>

참고

- 한 입 크기로 잘라 먹는 리액트 - 이정환
