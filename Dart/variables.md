### Variables

#### 변수 선언 방법

1. `var` keyword
2. 명시적으로 변수의 타입 지정하기

```dart
void main() {
    var name = 'sehyun';
    name = 'ra'; // 재할당

    String address = 'seoul';
}
```

`var` 키워드로 선언한 변수에 새로운 값을 재할당할 때, 처음에 할당한 값과 다른 자료형의 값을 할당할 수 없음 (위의 `name` 변수에 `11` 같이 문자열이 아닌 값 할당 불가능)  
보통 **함수나 메서드 내부에 지역 변수 선언할 때는 var**, **클래스에서 변수나 프로퍼티를 선언할 때에는 타입 지정**

#### `dynamic`

여러가지 타입을 가질 수 있는 변수에 쓰는 키워드 (not recommended but sometimes very useful)

```dart
void main() {
    var dnm; // type: dynamic

    dnm = 'sehyun';
    dnm = 11;
    dnm = true;
}
```

위처럼 `var dnm;`이라고 하지 않고 `dynamic dnm;`처럼 dynamic이라는 걸 명시해 줄 수도 있음
