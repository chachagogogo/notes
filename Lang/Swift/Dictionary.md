```swift
var responseMessages = [200: "OK",
                        403: "Access forbidden",
                        404: "File not found",
                        500: "Internal server error"]


let httpResponseCodes = [200, 403, 301]
for code in httpResponseCodes {
    let message = responseMessages[code, default: "Unknown response"]
    print("Response \(code): \(message)")
}
// Prints "Response 200: OK"
// Prints "Response 403: Access forbidden"
// Prints "Response 301: Unknown response"

Dict.isEmpty
Dict.count
// value, key 순서 유의.
// 없는 키 넣으면 nil 리턴. 키 있으면 수정 이전의 value를 리턴.
Dict.updateValue("value", forKey: "key")
// Dict["key"] = nil로도 지울 수 있음
// 없는 키 넣으면 nil 리턴. 키 있으면 삭제된 value를 리턴.
Dict.removeValue(forKey: "key")

for (key, value) in Dict {
	print("\(key) \(value)")
}
```

## Parameters
`key`
The key the look up in the dictionary.

`defaultValue`
The default value to use if `key` doesn’t exist in the dictionary.


