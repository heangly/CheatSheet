Create Observable.swift and add this
```swift
class Observable<T> {
    var value: T? {
        didSet {
            listener?(value)
        }
    }

    private var listener: ((T?) -> Void)?

    init(_ value: T?) {
        self.value = value
    }

    func bind(_ listener: @escaping (T?) -> Void) {
        listener(value)
        self.listener = listener
    }
}


```

Inside ViewModel
```swift

struct FeedViewModel {
    var tweets: Observable<someModel> = Observable([])
}

```

Bind like this in ViewController
```swift

    func bindToViewModel() {
        viewModel.someVariable.bind { [weak self] someResultValues in
  
        }
    }

```
