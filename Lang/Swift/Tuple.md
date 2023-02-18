- 한번 선언되면 추가, 삭제 불가능
- 배열, 딕셔너리와는 다르게 여러 종류의 타입 저장 가능
```swift
var tpl1: (String, int) = ("Sample String", 1) 
var tpl2: (String) = ("Sample String") // 이렇게 아이템이 하나면 튜플이 아니라 해당 타입임

// 점 찍어서 인덱스 조회 가능. 순회는 안됨.
let tupleValue = ("a", "b", 1, 2.5, true)
tupleValue.0 // "a"
tupleValue.1 // "b"
tupleValue.2 // 1
tupleValue.3 // 2.5
tupleValue.4 // true
```

## 바인딩
- 매우 편리함
- 개수가 일치해야 함
```swift
let (a, b, c, d, _) = tupleValue // 5개로 선언했으니 바인딩도 5개 맞춰줘야 함
```