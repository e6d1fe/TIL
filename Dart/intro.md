### Introduction to Dart

https://dart.dev/language

#### Hello World

Every app requires the top-level `main()` function.  
Functions that don't have an explicit return value have the `void` return type.

```dart
void main() {
    print('Hello World');
}
```

#### Variables

You can declare most variables using `var` without explicitly specifying their type.  
When declared using `var`, these variables' types are determined by their initial values.

#### Control Flow Statements

```dart
if (year >= 2001) {
    print('21st century');
} else if (year >= 1901) {
    print('20th century');
}

for (final object in flybyObjects) {
    print(object);
}

for (int month = 1; month <= 12; month++) {
    print(month);
}

while (year < 2016) {
    year += 1;
}
```

#### Functions

Specifying the types of each function's arguments and return value is recommended.

#### Comments

Dart comments usually start with `//`, but you can also use comments like `/* this */`.

#### Imports

```dart
// Importing core libraries
import 'dart:math';

// Importing libraries from external packages
import 'package:test/test.dart';

// Importing files
import 'path/to/my_other_file.dart';
```

#### Important Concepts

- Everything you can place in a variable is an object, and every object is an instance of a class. Even numbers, functions, and `null` are objects.
- Although Dart is strongly typed, type annotations are optional because Dart can infer types.
- If you enable null safety, variables can't contain `null` unless you say they can. You can make a variable nullable by putting a question mark at the end of its type.
- When you want to explicitly say that any type is allowed, use the type `Object?` (if you've enabled null safety) or `Object`.
- Unlike Java, Dart doesn't have the keywords `public`, `protected`, and `private`. If an identifier starts with an underscore, it's private to its library.
- Warnings are just indicators that your code might not work, but they don't prevent it from executing. Errors can be either compile-time or run-time. A compile-time error prevents the code from executing at all; a run-time error results in an exception being raised while the code executes.
