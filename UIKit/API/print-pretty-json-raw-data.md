
Add this extension in a new file
```swift
extension Data {
    var printPrettyJSON: NSString? {
        guard let object = try? JSONSerialization.jsonObject(with: self, options: []),
              let data = try? JSONSerialization.data(withJSONObject: object, options: [.prettyPrinted]),
              let printPrettyJSON = NSString(data: data, encoding: String.Encoding.utf8.rawValue) else { return nil }

        return printPrettyJSON
    }
}
```

Usage: after getting raw data back API call, just type ```swift data.printPrettyJSON ```