``` swift

// Passing data from B back to A

// class A
class MyViewController: UIViewController {
    override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
    
        guard let destinationController = segue.destinationViewController as? DestinationViewController else { return }
    	// receiving the data back
        destinationController.onCompletion = { success in
            // this will be executed when `someButtonTapped(_:)` will be called
            print(success)
        }
    }
}


// class B
class DestinationViewController: UIViewController {
	// define optional closure signature
    var onCompletion: ((success: Bool) -> ())?

    @IBAction func someButtonTapped(sender: AnyObject?) {
	// passing the data back
        onCompletion?(success: true)
    }
}

```