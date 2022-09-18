< [Back to Portfolio Page](README.md)
# CS/Swift Fundamentals

## <a href = "https://github.com/raywenderlich/swift-algorithm-club/tree/master/Insertion%20Sort">Insertion Sort</a>
Goal: Sort an array from low to high (or high to low).

* You are given an array of numbers and need to put them in the right order. The insertion sort algorithm works as follows:

1. Put the numbers on a pile. This pile is unsorted.
2. Pick a number from the pile. It doesn't really matter which one you pick, but it's easiest to pick from the top of the pile.
3. Insert this number into a new array.
4. Pick the next number from the unsorted pile and also insert that into the new array. It either goes before or after the first number you picked, so that now these two numbers are sorted.
5. Again, pick the next number from the pile and insert it into the array in the proper sorted position.
6. Keep doing this until there are no more numbers on the pile. You end up with an empty pile and an array that is sorted.

```
func insertionSort(_ array: [Int]) -> [Int] {
    var sortedArray = array			 // 1
    for index in 1..<sortedArray.count {		 // 2
        var currentIndex = index
        while currentIndex > 0 && sortedArray[currentIndex] < sortedArray[currentIndex - 1] { // 3
            sortedArray.swapAt(currentIndex - 1, currentIndex)
            currentIndex -= 1
        }
    }
    return sortedArray
}
```
Here is how the code works.

Make a copy of the array. This is necessary because we cannot modify the contents of the array parameter directly. Like Swift's own sorted(), the insertionSort() function will return a sorted copy of the original array.

There are two loops inside this function. The outer loop looks at each of the elements in the array in turn; this is what picks the top-most number from the pile. The variable currentIndex is the index of where the sorted portion ends and the pile begins (the position of the | bar). Remember, at any given moment the beginning of the array -- from index 0 up to currentIndex -- is always sorted. The rest, from index currentIndex until the last element, is the unsorted pile.

The inner loop looks at the element at position currentIndex. This is the number at the top of the pile, and it may be smaller than any of the previous elements. The inner loop steps backwards through the sorted array; every time it finds a previous number that is larger, it swaps them. When the inner loop completes, the beginning of the array is sorted again, and the sorted portion has grown by one element.

Note: The outer loop starts at index 1, not 0. Moving the very first element from the pile to the sorted portion doesn't actually change anything, so we might as well skip it.

### No More Swap

Instead of swapping with each of the previous elements, we can just shift all those elements one position to the right, and then copy the new number into the right position.

```
[ 3, 5, 8, 4 | 6 ]   remember 4
           *

[ 3, 5, 8, 8 | 6 ]   shift 8 to the right
        --->
        
[ 3, 5, 5, 8 | 6 ]   shift 5 to the right
     --->
     
[ 3, 4, 5, 8 | 6 ]   copy 4 into place
     *
```
In code that looks like this:

```
func insertionSort(_ array: [Int]) -> [Int] {
  var sortedArray = array
  for index in 1..<sortedArray.count {
    var currentIndex = index
    let temp = sortedArray[currentIndex]
    while currentIndex > 0 && temp < sortedArray[currentIndex - 1] {
      sortedArray[currentIndex] = sortedArray[currentIndex - 1]                // 1
      currentIndex -= 1
    }
    sortedArray[currentIndex] = temp                      // 2
  }
  return sortedArray
}
```
The line at //1 is what shifts up the previous elements by one position. At the end of the inner loop, y is the destination index for the new number in the sorted portion, and the line at //2 copies this number into place.

### Making it generic
```
func insertionSort<T>(_ array: [T], _ isOrderedBefore: (T, T) -> Bool) -> [T] {
  var sortedArray = array
  for index in 1..<sortedArray.count {
      var currentIndex = index
      let temp = sortedArray[currentIndex]
      while currentIndex > 0 && temp < sortedArray[currentIndex - 1] {
        sortedArray[currentIndex] = sortedArray[currentIndex - 1]                // 1
        currentIndex -= 1
      }
      sortedArray[currentIndex] = temp                      // 2
    }
    return sortedArray
 }
```
```
let numbers = [ 10, -1, 3, 9, 2, 27, 8, 5, 1, 3, 0, 26 ]
insertionSort(numbers, <)
insertionSort(numbers, >)
```

```
let objects = [ obj1, obj2, obj3, ... ]
insertionSort(objects) { $0.priority < $1.priority }
```
if two objects have the same priority, regardless of the values of their other properties, those two objects don't get swapped around.

### Performance
The worst-case and average case performance of insertion sort is O(n^2). That's because there are two nested loops in this function. Other sort algorithms, such as quicksort and merge sort, have O(n log n) performance, which is faster on large inputs.

Insertion sort is actually very fast for sorting small arrays. Some standard libraries have sort functions that switch from a quicksort to insertion sort when the partition size is 10 or less.






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
