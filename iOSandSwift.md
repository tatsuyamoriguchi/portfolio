< [Back to Portfolio Page](README.md)

# iOS and Swift
A partial list of iOS and Swift projects topics learned

## Software Development Lifecycle
* <a href="https://youtu.be/gNmrGZSGK1k">What Are The Steps of the Software Development Lifecycle?</a>
* <a href="https://youtu.be/ZrEHmUZ4OeY">iOS Swift - 00B1 Workflow (Software Development Life Cycle)</a>
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
- [x] <a href="https://clearbridgemobile.com/how-to-build-a-mobile-app-requirements-document/">How to Write an Effective Mobile App Product Requirements Document</a>
- [x] <a href="https://nix-united.com/blog/how-to-write-a-proper-mobile-app-requirements-document-in-5-steps/">HOW TO WRITE A PROPER MOBILE APP REQUIREMENTS DOCUMENT IN 5 STEPS</a>
- [x] <a href="https://lvivity.com/functional-and-non-functional-requirements">FUNCTIONAL AND NON-FUNCTIONAL REQUIREMENTS FOR MOBILE APP: WHAT’S THE DIFFERENCE?</a>

3. Design
* Business Rules
* Layout
* Color Scheme
* Wireframe/sketch
* Programming language to use
* Frameworks, SDKs, APIs
* Back-end system server design
* Database design and relationship (data design)
* Mobile Devices, OS versions, browser, and other external software to support
* <a href="https://www.k7tech.agency/blog/ios-app-architecture-patterns">App architecture: A brief introduction to the iOS app architecture patterns</a>
  * App architecture essentially presents a set of techniques and patterns which help developers create a well-structured application.
  * App architectures help prevent code duplication, bad programming practices, and messy code. 
  * The model represents knowledge - data structures, business logic, and rules. It is completely independent of the user interface.The view serves as a presentation of data - screens with UI elements where data is displayed and can be modified by the user.
  * **MVC**: In the MVC pattern, the instructions are managed by the Controller - the layer where all the wires should be connected. It’s usually least reusable part of the app since it contains domain-specific rules. It “owns” the Model and uses it to define the flow of information. Think of it as an engine or brain - it decides what happens next. Problem with MVC (at least in iOS environment) is that ViewControllers, which should represent a part of the Controller layer, contains partial state and logic of the View layer. This usually leads to massive ViewControllers and bulky files.
  * **MVP** (Model-View-Presenter): MVP is an alternative to the MVC pattern where the Controller is replaced by the Presenter. In this case, the separation of concerns is as follows: ViewController is a part of the View layer only, including all the UI setups and events. The Presenter is the component dealing with all-things-logic.The Model stays the same. It’s important to note that MVP uses passive View pattern, which means that all the actions will be forwarded to the Presenter. It will then trigger the UI updates using delegates and the View will only pass actions and listen to the Presenter updates.
  * **MVVM** (Model-View-View Model): The MVVM pattern also allows taking some of this presentation logic out of the ViewController. It introduces View Model - layer that has been described as a state of the data in the View - which allows the creation of customized Models for each View. The idea of MVVM architecture is to have bindings between View and ViewModel which provide automatic synchronization of data and visual representation. This helps avoid the boilerplate code. View-ViewModel separation is particularly convenient because developers can work on ViewModel code and designers can work on View in Interface Designer.
  * **VIPER**: The word VIPER is an acronym for View, Interactor, Presenter, Entity, and Routing. This so-called Clean Architecture pattern divides the app’s logical structure into distinct layers of responsibility. Consequently, it is easier to isolate dependencies (e.g. your database) and to test the interactions at the boundaries between layers. VIPER’s distinct layers help deal with this challenge by providing clear locations for application logic and navigation-related code.
  * MVC results in poor testing process - only Model can be examined, V&C (due to the tight connection they have) cannot be tested at all. The robust connection between Controller and View segments proved to be truly “unhealthy” when it comes to software, so a new pattern was developed quickly after. However, it still is the “starter” pattern, the one that developers mostly begin with and improve over time. It should be used for simple and small apps.
  * Some variations of this simple app design include transition to MVP. Its added benefit is that the View is more loosely coupled to the Model and it is easier to unit test it because interaction with the View is through an interface. Both MVC and MVP can be quite clean when implemented correctly, so this makes it more of a personal choice.
  * MVVM’s distribution pattern is better than in MVC, but it is massively overloaded compared to MVP. Testing is of particular importance here. While writing the code you cannot guarantee that the whole project will function properly; tests help to ensure it will. MVVM provides great testing ground. MVVM should be used for medium-to-large applications and is generally not the pattern intended for new developers as it requires a bit more skill to be implemented correctly. Nevertheless, it is a great paradigm that stands on its own and is only made better with a nice binding framework. The motivation behind MVVM in iOS is that it essentially reduces the complexity of one’s view controllers (combating massive view controller syndrome) and makes one’s presentation logic easier to test.
  * This is also the case with VIPER. Its module separation is very beneficial once it comes to unit tests, as the great pattern’s distribution lets you test all the functionalities available. This architecture is intended for large applications since its benefits are not so relevant and noticeable in small apps.

<a href ="https://intellipaat.com/blog/tutorial/ios-tutorial/ios-architecture/">iOS Architecture</a>
Architecture of IOS is a layered architecture. At the uppermost level iOS works as an intermediary between the underlying hardware and the apps you make. Apps do not communicate to the underlying hardware directly.
Apps talk with the hardware through a collection of well defined system interfaces. These interfaces make it simple to write apps that work constantly on devices having various hardware abilities.
Lower layers gives the basic services which all application relies on and higher level layer gives sophisticated graphics and interface related services.
Apple provides most of its system interfaces in special packages called frameworks. A framework is a directory that holds a dynamic shared library that is .a files, related resources like as header files, images, and helper apps required to support that library. Every layer have a set of Framework which the developer use to construct the applications.

### Core OS Layer:
1. The Core OS layer holds the low level features that most other technologies are built upon.

| Core Bluetooth Framework |
| --- |
| Accelerate Framework |
| External Accessory Framework |
| Security Services framework |
| Local Authentication framework |
| 64-Bit support from IOS7 supports the 64 bit app development and enables the application to run faster |



2. Core Services Layer
Some of the Important Frameworks available in the core services layers are detailed:

| Core Services Layer Features | Description |
| --- | --- |
| Address book framework | – Gives programmatic access to a contacts database of user. |
| Cloud Kit framework | – Gives a medium for moving data between your app and iCloud. |
| Core data Framework | – Technology for managing the data model of a Model View Controller app. |
| Core Foundation framework | – Interfaces that gives fundamental data management and service features for iOS apps. |
| Core Location framework | – Gives location and heading information to apps. |
| Core Motion Framework | – Access all motion based data available on a device. Using this core motion framework Accelerometer based information can be accessed. |
| Foundation Framework | – Objective C covering too many of the features found in the Core Foundation framework |
| Healthkit framework | – New framework for handling health-related information of user |
| Homekit framework | – New framework for talking with and controlling connected devices in a user’s home. |
| Social framework | – Simple interface for accessing the user’s social media accounts. |
| StoreKit framework | – Gives support for the buying of content and services from inside your iOS apps, a feature known asIn-App Purchase. |

3. Media Layer
Graphics, Audio and Video technology is enabled using the Media Layer.

| Graphics Framework | Description |
| --- | --- |
| UIKit Graphics | – It describes high level support for designing images and also used for animating the content of your views. | 
| Core Graphics framework | – It is the native drawing engine for iOS apps and gives support for custom 2D vector and image based rendering. |
| Core Animation | – It is an initial technology that optimizes the animation experience of your apps. |
| Core Images | – gives advanced support for controling video and motionless images in a nondestructive way |
| OpenGl ES and GLKit | – manages advanced 2D and 3D rendering by hardware accelerated interfaces |
| Metal | – It permits very high performance for your sophisticated graphics rendering and computation works. It offers very low overhead access to the A7 GPU. |

4. Audio Framework
| Audio Framework Features | Description |
| --- | --- |
| Media Player Framework | – It is a high level framework which gives simple use to a user’s iTunes library and support for playing playlists. |
| AV Foundation | – It is an Objective C interface for handling the recording and playback of audio and video. |
| OpenAL | – is an industry standard technology for providing audio. |

5. Video Framework

| Video Framework | Description |
| --- | --- |
| AV Kit | – framework gives a collection of easy to use interfaces for presenting video. |
| AV Foundation | – gives advanced video playback and recording capability. |
| Core Media | – framework describes the low level interfaces and data types for operating media. |


6. Cocoa Touch Layer

| Cocoa Touch Layer | Description |
| --- | --- |
| EventKit framework | – gives view controllers for showing the standard system interfaces for seeing and altering calendar related events |
| GameKit Framework | – implements support for Game Center which allows users share their game related information online |
| iAd Framework | – allows you deliver banner-based advertisements from your app. |
| MapKit Framework | – gives a scrollable map that you can include into your user interface of app. |
| PushKitFramework | – provides registration support for VoIP apps. |
| Twitter Framework | – supports a UI for generating tweets and support for creating URLs to access the Twitter service. |
| UIKit Framework | – gives vital infrastructure for applying graphical, event-driven apps in iOS. Some of the Important functions of UI Kit framework: Multitasking support, Basic app management and infrastructure, User interface management, Support for Touch and Motion event, Cut, copy and paste support and many more. |





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
