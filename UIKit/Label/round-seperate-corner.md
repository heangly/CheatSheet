top left, top right, bottom left, bottom right. If any side of corner is not wanted, just delete it.

```swift
label.layer.maskedCorners = [.layerMaxXMinYCorner, .layerMinXMinYCorner, .layerMaxXMinYCorner, .layerMinXMinYCorner]

```