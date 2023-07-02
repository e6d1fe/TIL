# useMemo

useMemo를 사용하면 특정 함수를 호출했을 때 그 반환값을 기억하고, 같은 함수를 다시 호출하면 기억해 두었던 값을 반환한다.

```
const value = useMemo(콜백함수, 의존성배열);
```

호출된 useMemo는 의존성 배열에 담긴 값이 바뀌면 콜백 함수를 다시 실행하고 결과값을 반환한다.<br>
예를 들어 다음과 같이 사용하면, count의 값이 변할 때만 연산을 수행해 그 값을 value에 저장한다.

```
const value = useMemo(() => {
    return count * count;
}, [count]);
```

이렇게 함수의 연산 결과를 기억해 성능을 최적화하는 것을 메모이제이션이라고 표현한다.
