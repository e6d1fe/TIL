### Metadata

https://dart.dev/language/metadata

Metadata can be used to provide additional information on your code.  
It begins with the character `@`.

- `@Deprecated`
- `@deprecated`
- `@override`
- `@pragma`

#### `@Deprecated`

`@Deprecated` can be used when you want to specify a message.

```dart
@Deprecated("use this instead")
```

You can use `@deprecated` instead when you don't want to specify a message, but it's recommended that you always use `@Deprecated` so that you can provide context.

#### Defining Your Own Metadata Annotations

```dart
class Todo {
  final String who;
  final String what;

  const Todo(this.who, this.what);
}

@Todo("dash", "implement this function")
void doSomething() {
  print("do something");
}
```
