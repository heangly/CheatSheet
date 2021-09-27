This is for seeing plain JSON that we get back without decode it.

``` swift

     do {
                    guard let result = try? JSONSerialization.jsonObject(with: data, options: .allowFragments) else { return }
                    print(result)

                } catch {

                }

```