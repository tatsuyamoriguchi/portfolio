< [Back to Portfolio Page](README.md)
# Sleep Tracer App Requirements

## Business Goals and Objectives
### Business problem or need to solve
* 70 Millions people in the US suffer from sleeping disorder. Potentially many more suffer from sleeping disorder but not aware of it.
* Educate and make them aware of the possibility of having sleeping disorder, and help their life better.
* Any fatigue, glockiness, muscle pain, dizziness indicate the possibility of sleeping disorder such as Sleep Apnea.
* Help people to easily access medical solutions and options.

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

### Unique Selling Points and Differentiation
* It gives a user an entry point to diagnosis his/her sleeping disorder just by iPhone and Apple Watch. Bluetooth-enabled Thermometor and devices will be options
* Although it's not a FDA certified medical device to diagnosis medical condition, it tells a user "the possibility" of unknown sleeping disorder, and gives him/her a chance to consult with a medical expert.

### Benefits that the app brings
* Helps users aware of potential sleeping disorder otherwise unknown to the users.
* As long as a user has an iPhone and Apple Watch, there is no cost to use.
* Discover potential patients for providers (clinics, hospitals, therapists, and medical device manufacturers).
* With in-app ad and payment, it helps providers to generate new leads and revenue.

### Monetization Model
* In-app Ad sponsor revenue
* In-app payment to directly purchase sponsor's products and services
* Highlight sponsor listing in a user's search of near-by interests list


## App User Personas and Stories
#### John Appleseed (Example, not real persona)
* Name: John Appleseed
* Demographic: 50 years old male living in Los Angeles, California, married with two college kids
* Occupation: Logistics Manager at e-Commerce company
* John's Story: John manages logistics staffs at a warehouse at multiple shifts. His work schedule changes every week. He usually wakes up at 6am, and drives to work by 8am. His regular work hours end at 5pm but usually work overtime till 6pm or 7pm.
* John's Challenges: Every morning he feels fatigue along with uncomfortable feeling on his neck and shoulder. He sometime wakes up in the middle of night or early morning. He's having a problem in sleeping through a night. 
* What John needs: Solutions or diagnosis of possible causes and expert advices and treatment. He however doesn't have knnowledge of sleeping disorder may be the cause of his morning glocky. And where to consult with.

## App features, functional and non-functional requirements
### App Features
* With wearing an Apple Watch paired with an iOS device while sleeping, a user's repsiratory and heart rate are recorded.
* A user needs to set up sleep schedule on his/her iOS device.
* The app monitors the threshold of respiratory and heart rate, and warns the user of illegular repiratory or heart rate recorded.
* Prompts the user with possible unaware sleeping disorder, and nearby expert information to consult with.
* Provides the user of the basic information about sleeping disorder, such as sleep apnea to educate.
* Providers can promote their services and products by using paid in-app ad feature. Paid sponsors are listed at the top of nearby expert information.
* In-app map shows nearby experts locations.
* Shows charts of respiratory and heart rates along with other optional health data recorded by Bluetooth devices, noise, and weather data such as local temperture, air pressure, humidity, wind speed and direction

### Functional Requirements
* iOS app pairing with an Apple Watch.
* Records health data (respiratory and heart data) from Apple Watch.
* Store the health data to HealthKit
* Access HealthKit to analyze illegular rate records.
* Display health data in charts.
* Display an advice to consult with experts if the data goes over the threshold.
* Display a list and map of nearby experts and sponsors.
* Display in-app ads.
* A user can schedule an appointment, in-app purchase sponsors' services and products.
* Display Google search list of each symptom such as sleep apnea.
* Access and download a user's health records from the user's clinic or hospital's FHIR server.

### Security Requirements
* Store user's health data in HealthKit
* Implement user's FHIR data access to external medical institutions' servers.
* Request access rights to user's health recrod in HealthKit and FHIR record.
### Performance Requirements
* For version 1, the number of simultaneous use of users is up to 1,000.
### Compatibility Requirements with Multiple Devices

| Device | Released	| First iOS |	Max iOS |
| ------------- | ------------- | ------------- | ------------- |
| iPhone SE (gen 3)	| 2022 | 15	| 16 BETA |
| iPhone 13 Pro / 13 Pro Max | 2021 | 15 | 16 BETA |
| iPhone 13 / 13 mini | 2021 | 15 | 16 BETA |
| iPhone 12 Pro / 12 Pro Max	| 2020	| 14 | 16 BETA |
| iPhone 12 / 12 mini | 2020 | 14 | 16 BETA |
| iPhone SE (gen 2)	13 | 2020 | 13 | 16 BETA |
| iPhone 11 Pro / 11 Pro Max	| 2019 | 13 | 16 BETA | 
| iPhone 11 | 2019 | 13 | 16 BETA |


| Device	| Released	| First iPadOS	| Max iPadOS | 
| --- | --- | --- | --- | 
| iPad Air (gen 5)	| 2022	| 15	| 16 BETA | 
| iPad (gen 9)	| 2021 | 15 | 16 BETA | 
| iPad mini (gen 6) |  2021 | 15 | 16 BETA | 
| iPad Pro 12.9" (gen 5)	| 2021 | 14 | 16 BETA |  
| iPad Pro 11" (gen 3) | 2021 | 14 | 16 BETA | 
| iPad Air (gen 4)	| 2020 | 14 | 16 BETA | 
| iPad (gen 8) | 2020 | 14 | 16 BETA | 
| iPad Pro 12.9" (gen 4)	| 2020 | 13 | 16 BETA |  

### Interrupt Requirements
* Battery low
* Battery full- when charging
* Incoming phone call
* Incoming SMS
* Incoming Alert from another mobile application
* Plugged in for charging
* Plugged out from charging
* Device shut off
* Application Update reminders
* Alarm
* Network connection loss
* Network connection restoration

1. Run in background: The interruption takes over while the application takes a back seat. It gains control after the interruption ends. For example, A phone call/Facetime that you attend while you are reading a digital book on iBooks(or similar application). When the user answers a phone, iBooks waits until it is done and then resumes when the call ends.
2. Show alert. Alert disappears, and you work as usual. ‘SMS received’- messages appear in the header. The user doesn’t bother about it and continue working with the application as normal. Other mobile app alerts, such as a new friend request on Facebook or WhatsApp message, also fall into this category. But if the user decides to read the message, the behavior described in Point 1 is followed. If ignored, the application’s state is unchanged.
3. Call to Action: Alarms have to be turned off or snoozed before you continue working. Same thing with App update messages. You either have to Cancel or Accept the changes before you proceed. Another example is that of the low battery alert- You can choose to continue as usual or go into a low power mode (if the device allows it.)
4. No impact: An example is: if a network connection becomes available and your device connects to it. Also, when you plug your device in for charging, no alert or call to action step is necessary. It will probably do its job while you continue using your application.


### Installtion and Launch Requirements
* Since 1st realease, no version update is necessary.
* Install the app via the App Store


### Localization Requirements
* Version 1 supports US and English locale. 

## App UX, user flow, design notice
(To be filled later)

## App technology and infrastructure requirements
* iOS
* watchOS
* HealthKit
* FHIR data access
* Core Data
* Core Motion
* Core Bluetooth
* External devices such as thermometer (TBD)
* Weather API
* CloudKit/Firebase (TBD)
* Push Notification
* Chart API or latest Apple's Chart/HealthKit Chart (TBD)
* Apple Maps Nearby Interests/Google Maps API (TBD)

## Assumptions, constraints & dependencies
* Consider to develop as Open Source Project.



## General Assets
(To be filled later)
* Icons of supported sizes (iOS: @1x @2x @3x images | Android: mdpi, hdpi, xhdpi, xxhdpi)
* Splash screens of recommended sizes (iOS: @1x @2x @3x images | Android: mdpi, hdpi, xhdpi, xxhdpi)
* Screenshots in the correct dimensions and required languages
* App descriptions in required languages
* Search keywords in required languages
* List of supported devices and OS versions
 

## Apple App Store
(To be filled later)
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

## Marketing Resouces
* Marketing regions
* App web site
* SNS channels to promote
* SEO
* SNS/Web site ad
* Analytic method
* Media promotion
