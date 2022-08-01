< [Back to Portfolio Page](README.md)
# Sleep Tracer (version 1) iOS App Development Plan
Sleep Tracer is a tentative app name.

## Product Concept
1. To provide a handy and easy to use tool to detect the possibility of a user’s sleep disorder symptom.
2. To educate users about sleep apnea and other sleeping issues
3. To give users health care options nearby for possible sleeping disorder and other symptoms
4. To promote clinics and institutions with Sleep Tracer

## Basic features and technologies to implement and learn
- [x] <a href="https://clearbridgemobile.com/how-to-build-a-mobile-app-requirements-document/">How to Write an Effective Mobile App Product Requirements Document</a>
- [x] <a href="https://nix-united.com/blog/how-to-write-a-proper-mobile-app-requirements-document-in-5-steps/">HOW TO WRITE A PROPER MOBILE APP REQUIREMENTS DOCUMENT IN 5 STEPS</a>
- [x] <a href="https://lvivity.com/functional-and-non-functional-requirements">FUNCTIONAL AND NON-FUNCTIONAL REQUIREMENTS FOR MOBILE APP: WHAT’S THE DIFFERENCE?</a>
- [ ] Software Development Lifecycle
- [ ] Designing software architecture and maintaining code quality
- [ ] Front end development UI/UX design -> SwiftUI with MVVM
- [ ] Combine
- [ ] Protocol Oriented Programming
- [ ] Functional Programming
- [ ] Enhance Debugging Technique
- [ ] <a href="https://medium.com/@mandrigin/ios-app-performance-instruments-beyond-48fe7b7cdf2">iOS App Performance: Instruments & beyond</a>
- [ ] <a href="https://www.raywenderlich.com/14223279-dependency-injection-tutorial-for-ios-getting-started ">Dependency Injection</a>
- [ ] Write Test Plan, Test Scenarios, and Test cases
- [ ] Unit Test with TDD
- [ ] UI test
- [ ] Integrate Circle CI.
- [ ] GitHub
- [x] Accessing HealthKit data (Respiratory reate)
- [ ] Loading respiratory data from Apple Watch for testing purpose.
- [ ] Analyze respiratory data with a threshold 
- [x] Research how respiratory data is recorded. What causes the time length variation between two measured points.
    * <a href="https://mashable.com/article/how-to-monitor-breathing-rate-apple-watch">How to monitor your breathing rate with Apple Watch</a>
    * <a href="https://www.sleepfoundation.org/sleep-apnea/sleep-respiratory-rate">Sleep Respiratory Rate</a>
    * Using its built-in accelerometer, the Apple Watch can track the number of breaths you take per minute while asleep.

| Age | Average Respiratory Rate |
| --- | --- |
| Newborn to 12 Months | 30 to 60 breaths per minute |
| 1 to 2 Years | 24 to 40 breaths per minute |
| 3 to 5 Years | 22 to 34 breaths per minute |
| 6 to 12 Years | 18 to 30 breaths per minute |
| 13 to 17 Years | 12 to 20 breaths per minute |
| 18 to 65 Years | 12 to 20 breaths per minute |
| 66 to 80 Years | 12 to 28 breaths per minute |
| 81 or older | 10 to 30 breaths per minute |

- [x] Low respiratory rate during sleep
    * Sleep Apnea
    * Asthma or other lung disorders
    * Heartburn
    * Pneumonia
    * Allergic reaction
    * Heart conditions and cardiac arrest
    * Drug use or overdose, particularly of a central nervous system depressant
- [x] High respiratory rate during sleep
    * tachypnea
    * hyperventilation
    * Anxiety and panic attacks
    * Asthma
    * Chronic obstructive pulmonary disease and other lung conditions
    * Lung infections such as pneumonia
    * Blood clot in one of the lung’s arteries
    * Heart failure
- [ ] Display an advice to make a appointment with a doctor nearby using Apple Maps' Nearby Points of Interest Searching
