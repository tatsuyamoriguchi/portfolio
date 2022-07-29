< [Back to Portfolio Page](README.md)

# iOS and Swift
A partial list of iOS and Swift projects topics learned

## CS/Swift Fundamentals
### <a href="https://github.com/raywenderlich/swift-algorithm-club/blob/master/Algorithm%20Design.markdown"> Algorithm design techniques</a>
* Use the similar problem's algorithm.
* OK to start with brute force
* breaking it down into bits and pieces and working your way up towards the solution.

### <a href=""> A note on Big-O notation</a>
* how much space it needs. Big-O notation gives you a rough indication of the running time of an algorithm and the amount of memory it 

Big-O	Name	Description
O(1)	constant	This is the best. The algorithm always takes the same amount of time, regardless of how much data there is. Example: looking up an element of an array by its index.
O(log n)	logarithmic	Pretty great. These kinds of algorithms halve the amount of data with each iteration. If you have 100 items, it takes about 7 steps to find the answer. With 1,000 items, it takes 10 steps. And 1,000,000 items only take 20 steps. This is super fast even for large amounts of data. Example: binary search.
O(n)	linear	Good performance. If you have 100 items, this does 100 units of work. Doubling the number of items makes the algorithm take exactly twice as long (200 units of work). Example: sequential search.
O(n log n)	"linearithmic"	Decent performance. This is slightly worse than linear but not too bad. Example: the fastest general-purpose sorting algorithms.
O(n^2)	quadratic	Kinda slow. If you have 100 items, this does 100^2 = 10,000 units of work. Doubling the number of items makes it four times slower (because 2 squared equals 4). Example: algorithms using nested loops, such as insertion sort.
O(n^3)	cubic	Poor performance. If you have 100 items, this does 100^3 = 1,000,000 units of work. Doubling the input size makes it eight times slower. Example: matrix multiplication.
O(2^n)	exponential	Very poor performance. You want to avoid these kinds of algorithms, but sometimes you have no choice. Adding just one bit to the input doubles the running time. Example: traveling salesperson problem.
O(n!)	factorial	Intolerably slow. It literally takes a million years to do anything.


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
