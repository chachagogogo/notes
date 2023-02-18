```toc
```

## 기본 모양
```swift
func add(num1: Int, num2: Int) -> Int {
	return num1 + num2
}
```

## typealias
```swift
// 튜플을 이렇게 지정해놓으면 h, g, n으로 접근 가능
typealias infoResult = (h: Int, g: Character, n: String)

func getUserInfo() -> infoResult {
	...
}

let info = getUserInfo()
info.h
info.g
info.n
```

## 외부 매개변수, 내부 매개변수
```swift
func printHello(to name: String, welcomeMsg msg: String) {
	print("\(name)에게: \(msg)")
}

printHello(to: "철수", welcomeMsg: "안녕~~")
```

## 매개변수 기본값
```swift
func printHello(to name: String, welcomeMsg msg: String = "반가워") {
	print("\(name)에게: \(msg)")
}

printHello(to: "철수", welcomeMsg: "안녕~~") // 철수에게: 안녕~~
printHello(to: "영희") // 영희에게: 반가워
```

## 인자 개수가 가변적일 때
```swift
func getAvg(score: Int...) -> Double {
	var total = 0
	for r in score {
		total += r
	}
	return (Double(total) / Double(score.count))
}
```

## InOut 매개변수: 함수 내에서 외부 스코프의 변수를 사용
- 우선, 함수 내에서 매개변수를 그대로 변경 할 수는 없다.
- 그래서 보통은 함수 내에서 매개변수와 동일한 이름의 변수를 만들어서 쓴다.
```swift
func incrementBy(base: Int) -> Int {
	var base = base // 매개변수와 동일한 이름의 변수 만들어서 사용
	base += 1
	return base
}
```

- 하지만 InOut 키워드로 외부 스코프의 변수를 그대로 사용할 수 있다(파이썬에서의 global 키워드와 비슷)
- 선언은 소괄호 내에서 한다
- 호출할 때에는 &연산자를 붙여서 메모리 주소값을 넘겨준다.
- 상수나 리터럴은 전달할 수 없다. 1오직 변수만 인자값으로 전달할 수 있다.
```swift
var count = 30

func foo(countArg: inout Int) -> Int {
	countArg += 1
	return countArg
}

print(foo(countArg: &count)) // 31
```