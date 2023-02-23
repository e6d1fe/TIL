## Computed property names

object에 적용되는 내용! <br />
allows you to put an expression in square brackets, which will be computed & used as a property name.
```
const propertyName = "example";

const obj = {
   [propertyName]: "hello",
};

console.log(obj);   // example: "hello"
```

## Spread syntax

array뿐만 아니라 object에도 적용 가능. <br />
```
const me = {
   name: "e6d1fe",
   age: 22,
   major: "ctm",
};

const cloneMe = {...me}; // shallow cloning 가능!
```

만약 shallow cloning을 하면서 특정 property의 값을 바꿔주고 싶다면, <br />
```
const cloneMe2 = {
   ...me,
   age: 55,
};
```
이렇게 하면 cloneMe2는 me 객체와 같은 내용을 가지지만 age의 값만 55로 바꿀 수가 있다.
