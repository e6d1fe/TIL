### Operators

#### Arithmetic Operators

| operator symbol | operator name    | description                                      |
| --------------- | ---------------- | ------------------------------------------------ |
| `+`             | addition         | for adding two operands                          |
| `-`             | subtraction      | for subtracting two operands                     |
| `-expr`         | unary minus      | for reversing the sign of the expression         |
| `*`             | multiplication   | for multiplying two operands                     |
| `/`             | division         | for dividing two operands with output in double  |
| `~/`            | integer division | for dividing two operands with output in integer |
| `%`             | modulus          | remainder after integer division                 |

```dart
void main() {
  int num1 = 48;
  int num2 = 5;

  int sum = num1 + num2;
  print(sum);

  int difference = num1 - num2;
  print(difference);

  int unaryMinus = -num1;
  print(unaryMinus);

  int mult = num1 * num2;
  print(mult);

  double div = num1 / num2;
  print(div);

  int intDiv = num1 ~/ num2;
  print(intDiv);

  int remainder = num1 % num2;
  print(remainder);
}
```

#### Relational Operators

| operator symbol | operator name | description                                                     |
| --------------- | ------------- | --------------------------------------------------------------- |
| `==`            | equal to      | checks if two operands are equal and returns boolean result     |
| `!=`            | not equal to  | checks if two operands are not equal and returns boolean result |

#### Type Test Operators

| operator symbol | operator name | description                                                |
| --------------- | ------------- | ---------------------------------------------------------- |
| `is`            | is            | returns boolean value if the object is a specific type     |
| `is!`           | is not        | returns boolean value if the object is not a specific type |
