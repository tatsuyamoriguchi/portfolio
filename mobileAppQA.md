< Back to <a href="https://tatsuyamoriguchi.github.io/portfolio/">Portfolio</a> July 26, 2022
# Mobile App QA Engineering Topics
(A partial list of mobile app QA engineering topics learned)

Tatsuya "Brian" Moriguchi

## Test Plan and High Level Procedures
### <a href="https://testlio.com/blog/step-step-mobile-application-testing-process/">Your step-by-step mobile application testing process</a> July 26, 2022
### Agile Testing and Continuous Integration

With an average sprint lasting 10 days, this means mobile app testing and preparation occurs throughout the entire development lifecycle. QA teams usually need to write test cases, while Dev teams are developing so that testing can happen in a short window at the end of the sprint.

Compared to Agile, CI is more of an iterative approach, in which code is developed in small, continuous updates and releases. Rather than testing an entire mobile application in a sprint, QA teams can test portions of a feature, or maybe 2 out of the 5 features done in that sprint. As code is produced in smaller segments, it is tested. End-to-end testing usually occurs prior to a release at the end of the sprint. 

### 1. Test scope & coverage
* Determine what you will test, specifically the features and functionality of the app.
* Determine the types of mobile app testing required: Functional Testing, Usability Testing, Compatibility Testing, Performance and Load Testing, Security Testing, Installation Testing, Localization Testing, Manual Testing, automated Testing, Mobile Device Testing.
* <a href="https://testlio.com/blog/9-step-mobile-app-testing-strategy-checklist/">9 Step Mobile app Testing Strategy</a>
  1. Cross-platform testing
  2. Feature functionality
  3. Type of application (Mobile-web, Natie, or Hybrid)
  4. Front-end testing (GUI): Regression tests, Performance checks, Changes or updates to app files that might break front-end functionality
  5. Back-end testing including security and performance tests
  6. Multiple network compatibility: Install and uninstall, Functionality, Traversal, Data exchange, UI
  7. Storage: Data space your app requires and how it affects monthly data plan.
  8. Data to and from: Load time, check network conditions, speciic deices, and geographic locations
  9. Applicaiton flow
* Specifics and Scope
  * Does the app interact with other apps?
  * Is the app Native or Mobile-web or Hybrid?
  * Is the app testing include only front-end or back-end testing as well?
  * Is it compatible with multiple networks?

#### Identify Testing Locations
Localization testing, which tests your app in a variety of locations and languages

#### Decide Device Coverage
* Leading mobile app companies test over 24 device-OS combinations prior to a release.
* What operating systems does your app support? 
* What are the earliest versions of the relevant OS? 
* What are the most popular mobile devices among your target audience? 

### 2. Plan mobile app tests
break the strategy down into a plan of action, detailing who / what will execute your tests and on what timeline. An essential component of this step is preparing test suites: writing test cases or test scripts for automated testing. 

#### Manual v Automated Testing
Automated testing is useful to verify repeated tasks and solid code. The drawback is that writing and updating the test scripts to verify an app’s standard features can be time consuming. automated scripts cannot substitute for ‘in the wild’ testing. 

#### Write Test Cases
<a href="https://testlio.com/blog/write-test-case-structured-project-team/">How to Write a Test Case for Your Project and Your Team</a>

#### Identify Testing Approach / Partner
When selecting testers (either with a crowdsourced QA company, or on your own), it is advantageous to use testers who are similar to your users.

### 3. Execute app testing
CI Systems and manaual testing in parallel

### 4. Track and manage defects
The key here is correctly prioritizing defects.
Defects can be tracked in a project management software like JIRA.
* Low: no major impact to business functionality (e.g. a misspelling in the UI)
* Medium: functionality is not working as expected, but there is a work around
* High: critical functionality is blocked, but there is a work around 
* Blocker: critical business functionality is blocked and the user has no work around

### 5. Review!
One option is to create <a href = "https://testlio.com/blog/8-steps-to-building-an-effective-qa-test-summary-report-for-mobile-applications/"a test summary report.</a>
* Which devices and OS versions were tested
* A review of the tests performed, and major defects uncovered 
* How many tests passed and failed
* If appropriate, you can also make a final recommendation on if the mobile application meets all the acceptance criteria and is ready for release to the public.



## Types of Test
### <a href="https://youtu.be/NgQT7miTP9M">Testing basics | Functional vs non-functional by Circle CI</a> July 25, 2022
Functional Testing: Confirms the code is doing the right thing, sets of specifications, no work-around
Non-Functional Testing: Confirms the code is doing it in the right way, properties that contributes the end user's experiences


| Hieralchy of Testing |
| ------------- |
| 6. Manual & Exploratory Tests |
| 5. Automated GUI Tests |
| 4. Acceptance Tests |
| 3. Integration Tests |
| 2. Component Tests |
| 1. Unit Tests |


## Unit Test
### <a href="https://x-team.com/blog/how-to-get-started-with-ios-unit-tests-in-swift/">HOW TO GET STARTED WITH IOS UNIT TESTS IN SWIFT</a> July 19, 2022
1. How to setup your Xcode project to support unit tests.
2. How to make your app code available for unit testing (@testable import yourApp)
3. How to create individual unit test cases.
4. How to write a basic iOS Unit test.
5. How awesome it is to be protected from regressions.

### <a href="https://youtu.be/F5aDfGNdsac" target="_blank">Getting Started With Unit Testing in Swift (XCTest, Test Cases, Code Coverage)</a> July 12, 2022

## UI Test
### <a href="https://youtu.be/rmKbsQ41wVY" target="_blank">UITesting iOS Tutorial</a> July 12, 2022

## Test Scenarios and Test Cases
### <a href="https://crediblesoft.com/how-to-test-mobile-app-guide-tutorial/" target="_blank">Mobile App Testing Scenarios & Test Cases</a> July 14, 2022
### <a href="https://www.guru99.com/testing-mobile-apps.html" target="_blank">Mobile Apps Testing: Sample Test Cases & Test Scenarios</a> July 14, 2022
### <a href="https://testlio.com/blog/9-mobile-app-test-cases/" target="_blank">9 Mobile App Test Cases</a> July 14, 2022
### <a href="https://www.testrigtechnologies.com/25-test-scenarios-for-mobile-app-testing/" target="_blank">The Top 25 test Scenarios for Mobile Applicaiton Testing in 2022</a> July 14, 2022

## JIRA Bug Tracking
### <a href="https://www.youtube.com/watch?v=IFE8n6fhfRA">jira Bug Tracking Tool Tutorial for Agile 🕷 Jira Bug Life Cycle</a> July 25, 2022
* Iteration Goal
* Backlog Items
* To Do
* In Progress
* Done

* Create a sub-task.
* Enter and update an estimated time in Log Work
* Check Scrum Board to monitor tasks for next daily standup.
* Check Burndown Chart.

* Create an issue
* Fill Title, Description
* Story points
* Steps to recreate/replicate
* Acceptance Criteria
* Environment
* Workaround


## CI/CO
### <a href="https://www.youtube.com/watch?v=VGVw8fnc5YY">iOS Continuous Integration Setup with CircleCI</a> July 24, 2022
How do multiple developers work together on the same Xcode project?
Version Control, Git/Github

DevA and Dev B both pulling code to make a local copy of a repository v1 from Github.
Dev A commits v2 back to the repo “committing/pushing/checking in your code” all the same meaning
Dev B trying to commit her v2 to the repo, Git detects the master source code has been changed (by Dev A) since Dev B checked it out at the last time. Dev B has to merge, which means getting the changed master code first and merge it with her local copy, fix whatever necessary then commit back to the repo.

How does a dev ensure that his code doesn’t break the project?
(Team of ten devs working on the same repo may produce a problem)

Answer: Unit testing

Break down your code into pieces of code. Write a test case, called unit test with dummy data.
Cannot cover all bugs, but you can sue it as the base line.

How do multiple devs maintain a consistent coding style?
Keep Coding convention and coding style
i.e. 
if i == 0 {
}
If i == 0
{
}
How many empty lines should be between two functions
Use SwiftLint to enforce coding convention and code style.
1. Before checking in any code into the repo, pull any updates and merge any changes properly.
2. Make sure that all the init tests still pass.
3. Run the lint tool and fix any code that doesn’t conform to the style guidelines set forth by the team.

Continuous Integration
Ci is. a process that monitors the repo and runs various checks and balances to ensure that the source code is in tiptop shape. CI ensures automatically build the project to make sure it runs, all unit tests are passed, Lint tool to check for code that doesn’t adhere coding conventions. Send a successful build to a QA environment or deliver iTunes for deployment into the App Store. These are automatically done by running on a specified schedule or whenever checks in code. If broken, notify appropriate people to fix the problem.

Commit to make a change to the local repository
Push the code to the remote repository
use the “git push” command to push the commits on the local repository to a remote repository.


Circle CI

Set up configuration file .circleci/config.yml

Set up Xcode scheme, which specifies which targets you want to build, what tests you want to run, what configuration do you want to use, etc.

Xcode/Manage Scheme/Check on Shared
Commit and Push to Github

config.yml

Jobs:
	job1:
		steps:
			- checkout
			- run command
			- run command
			- save output
	job2:
		steps:
			-
			-
	job3:

workflows: // you can specify which job you want to run
	workflow1:
		jobs:
			- job1
			- job3

Fastlane works with Circle CI and helps tedious process automatize.
Integrate lint tool to check coding style to Circle CI as a job.
 
### <a href="https://www.youtube.com/watch?v=vTsKCEZA5Eo">Automate iOS Deployment to App Store Test Flight Using **Fastlane**</a> July 21, 2022

May become tedious to manually build your app by opening Xcode, select Generic for a deice type, set a version number, run Archive, and open a web browser to upload the build to App Store Connect and TestFlight.

<a href="https://fastlane.tools">Fastlane</a> is a commandline tool to automate to build and release mobile apps.
* To install, type '% brew install fastlane' using a homebrew package manager for Mac.
* To set up fastlane, go to your project directory in Terminal, type '% fastlane init'
* Select one:
     * Automate Screenshots
     * Automate beta distribution to TestFlight
     * Automate App Store distribution
     * Manual setup to automate your tasks

* Type your Apple ID and password, then Apple ID verification code.
* Open Fastfile to see the automation script.
* Go to your app directory in Terminal, type '% fastlane beta'
* If Tranporter Error occures, create App specific password. Go to appleid.apple.com, find "APP-SPECIFIC PASSWORDS" and click "Generate password...", type a password label then click 'Create' to auto-generate a passowrd.
* Go back to Terminal and paste the password and hit an Enter key.
* Access App Store Connect page if the upload was successful.

### <a href="https://www.youtube.com/watch?v=_dfLOzuIg2o">What is Docker?</a> July 21, 2022
  *  Docker is a containerized virtual environment that makes it easy to develop, maintain, and deploy apps and services.
  *  Start with accessing DockerHub, online cloud repository of Docker containers.
  *  Dockerfile, which can be built in a DockerImage, which can be run as a Docker Container

### <a href="https://stackshare.io/stackups/appium-vs-circleci">Appium vs CircleCI: What are the differences?</a> July 21, 2022
  *  Appium: classified as "Mobile Testing Frameworks", Automation for iOS and Android Apps. Appium is an open source test automation framework for use with native, hybrid, and mobile web apps. It drives iOS and Android apps using the WebDriver protocol. Appium is sponsored by Sauce Labs and a thriving community of open source developers
  *  CircleCI: classified as "Continuous Integration" tools, Automate your development process quickly, safely, and at scale. Continuous integration and delivery platform helps software teams rapidly release code with confidence by automating the build, test, and deploy process. Offers a modern software development platform that lets teams ramp.
  *  Features offered by Appium are: 
     *  Works on native and hybrid mobile apps
     *  Write mobile tests using any language or framework
     *  Open source
  * Features offered by CircleCI:
     * Language-Inclusive Support
     * Custom Environments
     * Flexible Resource Allocation
     * "Webdriverio support" is the primary reason why developers consider Appium over the competitors, whereas "Github integration" was stated as the key factor in picking CircleCI.
### <a href="https://youtube.com/playlist?list=PL9GgS3TcDh8x6tcY7HDq2zmEx0fAtwWsM" target="_blank">How to get started with Circle CI</a> July 12, 2022

## TDD & BDD
### <a href="https://www.youtube.com/watch?v=0TGQpZiAoKU">TDD and Unit Testing in iOS | Part 2 Stateful Objects</a>
* Test a stateful object's state changes.
* Icrementally write a unit test then function.
* 
### <a href="https://youtu.be/B4yJ85IaTUw">TDD and Unit Testing in iOS | Part 1 Stateless Objects</a> July 25, 2022
* Always write a test before writing a function.
* Start writing the simplist test, and write a code for it, then expand and repeat it, incrementally.
* When creating a new test file and class, use 'tests' at the end of its name: class MoneyFormatterTests: XCTestCase {
* When creatung a new test file and class, add '@testable import WeeklyBudget', for instance, to access necessary objects in the project.
* 
### <a href="https://youtu.be/mT8QDNNhExg" target="_blank">BDD vs TDD (explained)</a> July 14, 2022
