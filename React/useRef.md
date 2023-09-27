# useRef

Ref = short for Reference

어떤 특정한 value를 참조할 때 사용한다.  
➡️ used frequently to manipulate the DOM!

1. ref object 선언하기

```
const inputRef = useRef(null);
```

2. manipulate하고 싶은 DOM 노드의 JSX에 ref 속성으로 위에서 선언한 ref object 추가하기

```
return <input ref={inputRef} />;
```

3. 그 다음에는 위 노드에 접근해서 `focus()` 같은 메소드를 사용할 수 있음

버튼을 눌렀을 때 특정 input이 포커스되도록 하고 싶은 경우 등에 사용함

<hr />

특정한 값을 참조할 때도 사용한다.

useRef는 값을 처음에 제공한 값으로 가지는 `current` property만을 가지는 ref object를 반환함
➡️ 정보를 저장하고 나중에 읽기 위해서 쓸 수 있음

`state`와 다른 점: 리렌더를 트리거하지 않는다.  
➡️ 컴포넌트의 외적 아웃풋에 영향을 주지 않는 정보를 저장하기에 좋다.  
➡️ 화면에 보여줄 정보를 저장하기에는 적합하지 않음. (이 경우에는 `state` 사용)
