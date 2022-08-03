< [Back to Portfolio Page](README.md)

# iOS and Swift
A partial list of iOS and Swift projects topics learned

## Software Development Lifecycle
1. Planning
* Feasibility Study: 
  * Can this project actually be completed? On time? Within budget? with existing staff?
  * Buy vs build?
2. Requirement Analysis
* Business rules
* Security requirements
* Use cases
* Sample screen designs
* Sample reports
* Approve by the customer prior to design work
3. Design
* Business Rules
* Layout
* Color Scheme
* Wireframe/sketch
* Programming language to use
* Frameworks, SDKs, APIs
* Back-end system server design
* Database design and relationship (data design)
* App acchitecture
* Mobile Devices, OS versions, browser, and other external software to support
4. Implementation/Coding
* Hardware Environment
* Coding
* Unit Test with TDD
* Designers continue graphic design.
* Testers start writing test plan, test scenarios, and test cases.
5. Testing
* Bug Lifecycle
  * Open
  * In Progress
  * Resolved
  * Closed
  * Re-opened
* CI(Circle CI)
* Test Automation (Appium)
* Types of tests
* Device tests
* Test Fight for beta testing
6. Deployment
* iOS app submission to the App Store
  * App name trade mark clearance
  * App name copyright clearance
  * App name retention at the App Store
  * iTunes Connect Account access
  * Company/Entity Name
  * App Store app listing name
  * Search keywords
  * Bundle id / SKU
  * Demo account for reviewers
  * Description
  * Support URL
  * Marketing URL
  * Privacy policy
  * App category
  * Copyright information
  * Contact information
  * App icon (1024×1024)
  * App Store distribution provision profile
  * App Store distribution code signing identity
  * Screenshots (correct sizes based on devices)
* Deployment automation tool (i.e. Fastlane)
* Enterprise distribution
* StoreKit
* (Test Fight)
7. Operation and Maintenance
* Monitor the server load
* Collect and manage bugs reported by users via technical and customer support teams
* Fix issues and make another release.


## CS/Swift Fundamentals
### <a href="https://github.com/raywenderlich/swift-algorithm-club/tree/master/Queue">Queue</a>
* A queue is a list where you can only insert new items at the back and remove items from the front.
* A queue gives you a FIFO or first-in, first-out order. The element you inserted first is the first one to come out.
```
queue.enqueue(10)
queue.enqueue(3)
queue.enqueue(57) // queue = [10,3, 57]
queue.dequeue // Returns 10 queue = [3, 57]
```
```
public struct Queue<T> {
  fileprivate var array = [T]()

  public var isEmpty: Bool {
    return array.isEmpty
  }
  
  public var count: Int {
    return array.count
  }

  public mutating func enqueue(_ element: T) {
    array.append(element)
  }
  
  public mutating func dequeue() -> T? {
    if isEmpty {
      return nil
    } else {
      return array.removeFirst()
    }
  }
  
  public var front: T? {
    return array.first
  }
}
```

More efficient dequeue code
```
public struct Queue<T> {
  fileprivate var array = [T?]()
  fileprivate var head = 0
  
  public var isEmpty: Bool {
    return count == 0
  }

  public var count: Int {
    return array.count - head
  }
  
  public mutating func enqueue(_ element: T) {
    array.append(element)
  }
  
  public mutating func dequeue() -> T? {
    guard head < array.count, let element = array[head] else { return nil }

    array[head] = nil
    head += 1
    
    // periodically trim down the array
    let percentage = Double(head)/Double(array.count)
    if array.count > 50 && percentage > 0.25 {
      array.removeFirst(head)
      head = 0
    }
    
    return element
  }
  
  public var front: T? {
    if isEmpty {
      return nil
    } else {
      return array[head]
    }
  }
}
```



### <a href="https://github.com/raywenderlich/swift-algorithm-club/tree/master/Stack">Stack</a>
* A stack is like an array but with limited functionality. You can only push to add a new element to the top of the stack, pop to remove the element from the top, and peek at the top element without popping it off.
* A stack gives you a LIFO or last-in first-out order.

```
public struct Stack<T> {
  fileprivate var array = [T]()

  public var isEmpty: Bool {
    return array.isEmpty
  }

  public var count: Int {
    return array.count
  }

  public mutating func push(_ element: T) {
    array.append(element)
  }

  public mutating func pop() -> T? {
    return array.popLast()
  }

  public var top: T? {
    return array.last
  }
}

```

### <a href="https://github.com/raywenderlich/swift-algorithm-club/blob/master/Algorithm%20Design.markdown"> Algorithm design techniques</a>
* Use the similar problem's algorithm.
* OK to start with brute force
* breaking it down into bits and pieces and working your way up towards the solution.

### <a href=""> A note on Big-O notation</a>
* how much space it needs. Big-O notation gives you a rough indication of the running time of an algorithm and the amount of memory it 

Big-O	Name	Description
* O(1)	constant	This is the best. The algorithm always takes the same amount of time, regardless of how much data there is. Example: looking up an element of an array by its index.
* O(log n)	logarithmic	Pretty great. These kinds of algorithms halve the amount of data with each iteration. If you have 100 items, it takes about 7 steps to find the answer. With 1,000 items, it takes 10 steps. And 1,000,000 items only take 20 steps. This is super fast even for large amounts of data. Example: binary search.
* O(n)	linear	Good performance. If you have 100 items, this does 100 units of work. Doubling the number of items makes the algorithm take exactly twice as long (200 units of work). Example: sequential search.
* O(n log n)	"linearithmic"	Decent performance. This is slightly worse than linear but not too bad. Example: the fastest general-purpose sorting algorithms.
* O(n^2)	quadratic	Kinda slow. If you have 100 items, this does 100^2 = 10,000 units of work. Doubling the number of items makes it four times slower (because 2 squared equals 4). Example: algorithms using nested loops, such as insertion sort.
* O(n^3)	cubic	Poor performance. If you have 100 items, this does 100^3 = 1,000,000 units of work. Doubling the input size makes it eight times slower. Example: matrix multiplication.
* O(2^n)	exponential	Very poor performance. You want to avoid these kinds of algorithms, but sometimes you have no choice. Adding just one bit to the input doubles the running time. Example: traveling salesperson problem.
* O(n!)	factorial	Intolerably slow. It literally takes a million years to do anything.


## iOS Frameworks
### SwiftUI
* <a href="https://youtu.be/RKfkG01x79w">Adding Text to SwiftUI</a> July 20, 2022
  * <a href="https://github.com/tatsuyamoriguchi/SwiftUISampleApp" target=_blank>Github repository - SwiftUISampleApp</a>
  * Very basic to use Text string and font style in View
  * Text("Hello, World").capitalized
  * .font(.title) // can be auto-sized by a user.
  * .font.system(size:24, weight: .semibold, design: .serif) // Cannot be auto-sizzed by a user.
  * The order of options matter.
  * .underline(), .italic(), .striethrough(), .baselineOffset(), .kerrning(), multilineTextAlignment(), .foregroundColor(), frame(width: , height: , alignment: )

## iOS System Design

## Xcode, Github, Tools
