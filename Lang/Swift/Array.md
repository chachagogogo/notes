## 배열 순회시 index를 이용하는 법

자바스크립트랑 비교하면 조금 불편하다
```swift
var cities = ["seoul", "tokyo", "new york"]

for city in cities {
	let index = cities.index(of: city)
	...
}
```
이런 방법도 있다
```swift
var cities = ["seoul", "tokyo", "new york"]

for (index, element) in cities.enumerated() {
  print("Item \(index): \(element)")
}
```

## 각종 메소드
```swift
Array.count
Array.isEmpty
Array.append(_:)
Array.insert(_: at:)
Array.append(contensOf:) // JS에서의 Array.concat()과 같다

var example1 = Array(repeating: "None", count: 3)
print(example1) // ["None", "None", "None"]

let example2 = [0, 1, 2, 3, 4] // Array 타입
let slicedExample2 = arr[1...3] // ArraySlice 타입
let example3 = Array(arr[1...3]) // Array 타입
```

