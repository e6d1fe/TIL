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

#### Nullable Variables

blocking references to `null`

```dart
// without null safety
bool isEmpty(String string) => string.length == 0;

main() {
    isEmpty(null); // runtime error - NoSuchMethodError
}
```

dart에서는 어떤 변수가 `null`이 될 수 있는지 명확히 표시해야 함

```dart
void main() {
  String? nico = 'nico';
  nico = null;
}
```

이렇게 타입 선언 키워드 끝에 `?`를 붙여 주면 `null`도 할당 가능한 변수가 됨  
그러면 컴파일러가 해당 변수의 값이 `null`이 될 수 있음을 알고 `String.length` 등의 메서드를 사용하기 전에 확인

```dart
void main() {
  String? nico = 'nico';
  nico = null;

  if (nico != null) {
    nico.length;
  }

  // same thing
  nico?.length;
}
```

All variables are non-nullable by default

https://dart.dev/language/variables

Variables store **references**.

```dart
var name = 'Bob';

Object name = 'Bob';

String name = 'Bob';
```

This variable called `name` contains a reference to a `String` object with a value of `'Bob'`.  
Its type is inferred to be a `String`, but you can change that by specifying it.  
If an object isn't restricted to a single type, specify the `Object` type or `dynamic` if necessary.  
Another option is to explicitly declare the type.

#### Null Safety

Null safety prevents an error that results from unintentional access of variables set to `null`.  
A null dereference error occurs when you access a property or call a method on an expression that evaluates to `null`.  
With null safety, **the Dart compiler detects these potential errors at compile time**.

1. When you specify a type for a variable, parameter, or another relevant component, you can control whether the type allows `null`. To enable nullability, you add a `?` to the end of the type declaration.
2. You must intialize variables before using them. **Nullable variables default to `null`**, so they are initialized by default.
3. You can't access properties or call methods on an expression with a nullable type. The same exception applies where it's a property or method that `null` supports like `hashCode` or `toString()`.

#### Default Value

Uninitialized variables that have a nullable type have an initial value of `null`.  
Even variables with numeric types are initially null, because numbers (like everything else in Dart) are objects.  
With null safety, you must initialize the values of non-nullable variables before you use them:

```dart
int? lineCount1;

int lineCount2 = 0;
```

**You don't have to initialize a local variable where it's declared, but you do need to assign it a value before it's used.**

#### Late Variables

The `late` modifier has two use cases:

1. Declaring a non-nullable variable that's initialized after its declaration.
2. Lazily initializing a variable.

If you're sure that a variable is set before it's used, but Dart disagrees, you can fix the error by marking the variable as `late`:

```dart
late String description;

void main() {
    description = 'Feijoada!';
    print(description);
}
```

If `description` above is not set as `late`, the following error appears: `The non-nullable variable 'description' must be initialized.`  
**If you fail to initialize a `late` variable, a runtime error occurs when the variable is used.**  
When you mark a variable as `late` but initialize it at its declaration, then the initializer runs **the first time the variable is used**.  
This lazy initialization is handy in a couple of cases:

1. The variable might not be needed right now, and initializing it is costly.
2. You're initializing an instance variable, and its initializer needs access to `this`.

In the following example, if the `temperature` variable is never used, then the expensive `readThermometer()` function is never called:

```dart
late String temperature = readThermometer(); // lazily initialized
```

#### Final and Const

If you never intend to change a variable, use `final` or `const` instead of `var` or in addition to a type.  
A final variable can be set only once; a const variable is a compile-time constant.

```dart
final name = 'Bob'; // without a type annotation
final String nickname = 'Bobby';
```

Use `const` for variables that you want to be compile-time constants.  
If the const variable is at the class level, mark it `static const`.  
You can also use the `const` keyword for creatinc constant values, as well as to declare constructors that create constant values.
