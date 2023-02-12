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
```

## Parameters
`key`
The key the look up in the dictionary.

`defaultValue`
The default value to use if `key` doesn’t exist in the dictionary.