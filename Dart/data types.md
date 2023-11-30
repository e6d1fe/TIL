### Data Types

Dart supports both dynamic and static types.

#### Static Types

The data types of statically typed variables are known at **compile time**.  
This helps the compiler detect issues or bugs quickly.  
You can use the `var` keyword to statically type a variable.

#### Dynamic Types

The data types of dynamically typed variables are known at **runtime**.  
You can use the `dynamic` keyword to dynamically type a variable.

- Numbers (`int`, `double`, `num`)
- Strings (`String`)
- Booleans (`bool`)
- Lists (`List`)
- Maps (`Map`)
- Sets (`Set`)
- Runes (`runes`)
- Null (`null`)

#### Numbers

`int`: 정수  
`double`: 소수  
`num`: 정수, 소수 모두

```dart
void main() {
  int num1 = 100;
  double num2 = 1.234;
  num num3 = 120;
  num num4 = 331.3;
}
```

#### Strings

```dart
void main() {
  String firstName = "Sehyun";
  String lastName = "Ra";

  print("My name is $firstName $lastName.");
}
```

To create a multi-line string, use triple quotes with either double or single quotation marks.

```dart
void main() {
  String multiLine = """
  Hi, my name is Sehyun Ra.
  I am 22 years old.
  I live in Seoul.
""";

  print(multiLine);
}
```

To create a raw string where special characters don't work, add `r` after the equal sign(`=`).

```dart
void main() {
  String notRawString = "Hi!\tNice to meet you.";
  String rawString = r"Hi!\tNice to meet you.";

  print(notRawString);
  print(rawString);
}
```

#### Booleans

```dart
void main() {
  bool isStudent = true;
}
```

#### Lists

Also called arrays.

```dart
void main() {
  List<String> coffees = ["latte", "americano", "cortado"];

  print(coffees[0]);
  print(coffees[1]);
  print(coffees[2]);
}
```

#### Sets

An unordered collection of unique items.

```dart
void main() {
  Set<String> weekdays = {
    "monday",
    "tuesday",
    "wednesday",
    "thursday",
    "friday"
  };
  print(weekdays);
}
```

#### Maps

An object where you can store data in key-value pairs.

```dart
void main() {
  Map<String, String> aboutMe = {
    "name": "Sehyun",
    "city": "Seoul",
    "country": "South Korea"
  };

  print(aboutMe["city"]);
}
```

You can specify the types of the keys and values.

#### Runes

Runes give you the unicode values of a string.

```dart
void main() {
  String value = "a";
  print(value.runes);
}
```

#### Type Conversion

| method           | from     | to       |
| ---------------- | -------- | -------- |
| `int.parse()`    | `String` | `int`    |
| `double.parse()` | `String` | `double` |
| `toString()`     | `int`    | `String` |
| `toInt()`        | `double` | `int`    |

#### How to Check Runtime Type

Use the `.runtimeType` method.

```dart
void main() {
  var value = "a";
  print(value.runtimeType);
}
```
