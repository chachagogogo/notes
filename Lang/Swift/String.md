
```swift
String.count // 문자열의 길이 리턴

String.uppercased()
String.lowercased()

String.hasPrefix('blah') // js에서의 String.prototype.startsWith()과 대응
String.hasSuffix('blah') // js에서의 String.prototype.endsWith()과 대응

String.append('newEl')
String.remove(at: 2)
String.removeAll()
String.contains('newEl') // bool 리턴
String.sorted()
String.reversed()
```

## Multi-line Strings
```swift
let movie = """
A day in
the life of an
Apple engineer
"""
```

## string interpolation

```swift
let name = "Taylor"
let age = 26
let message = "Hello, my name is \(name) and I'm \(age) years old."
print(message)
```

