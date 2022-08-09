# CS/Swift Fundamentals
## <a href="https://github.com/raywenderlich/swift-algorithm-club/tree/master/Queue">Queue</a>
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



## <a href="https://github.com/raywenderlich/swift-algorithm-club/tree/master/Stack">Stack</a>
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

## <a href="https://github.com/raywenderlich/swift-algorithm-club/blob/master/Algorithm%20Design.markdown"> Algorithm design techniques</a>
* Use the similar problem's algorithm.
* OK to start with brute force
* breaking it down into bits and pieces and working your way up towards the solution.

## <a href=""> A note on Big-O notation</a>
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
