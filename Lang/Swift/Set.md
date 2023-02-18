```toc
```
- hashable data만 set로 만들 수 있음
	- built-in 타입은 모두 O
	- 사용자가 만든 타입은 Hashable 프로토콜로 구현해야 함

```swift
let people = Set([
    "Denzel Washington",
    "Tom Cruise",
    "Nicolas Cage",
    "Samuel L Jackson"
    ])

Set.isEmpty
Set.count
Set.contains('blah')
Set.insert('blah')
Set.remove('bla')
Set.removeAll()
Set.sorted()

a.intersection(b) // 교집합
a.union(b) // 합집한
a.symmetricDifference(b) // 합집합 - 교집합
a.subract(b) // 차집합. 리턴 값이 없음.

a.isSubset(of:) // 부분집합
a.isSuperset(of:) // 상위집합
a.isStrictSubset(of:) // 자기 자신과 같은 집합이 아닌 부분집합
a.isStrictSuperset(of:) // 자기 자신과 같은 집합이 아닌 상위집합
a.isDisjoint(with:) // 배반관계인지
```

```swift
let students: Set = ["Kofi", "Abena", "Peter", "Kweku", "Akosua"]
let sortedStudents = students.sorted()
print(sortedStudents)
// Prints "["Abena", "Akosua", "Kofi", "Kweku", "Peter"]"
```

## Array 중복원소 제거 팁
```swift
A = Array(Set(A))
```