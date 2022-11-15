# HealthKit and HIPAA Compliance

Reference: What Developers Need to Know About Apple’s HealthKit and HIPAA Compliance | App Developer Magazine 
https://appdevelopermagazine.com/what-developers-need-to-know-about-apple’s-healthkit-and-hipaa-compliance/

In the States, this personally identifiable health information, once shared with an entity like a hospital or doctor is subject to the Health Information Portability and Accountability Act [(HIPAA)](https://www.hhs.gov/hipaa/index.html) protections and compliance requirements. 

Covered Entities are the health care providers and payers that people use to get and pay for health services. From doctors, to clinics, hospitals and insurers, these organizations provide and pay for healthcare. 

Protected Health Information (PHI) is the personally identifiable health information that patients share with covered entities in the course of care. PHI can be everything from test results, to MRI scans, to something as simple as appointment schedules and phone logs. 

Business Associates are the companies and third parties that manage protected health data on behalf of covered entities in the process of providing service to patients. Business associates include the application developers building new apps for Apple’s HealthKit, hosting providers that handle PHI, and other offline service providers. If you’re building an application that handles, or could handle PHI, you are considered by law - whether you want to be or not - a Business Associate.

HIPAA does not have a recognized third party certification entity. While compliance is required, HIPAA states that application creators alone are responsible for ensuring compliance with the law. There are companies that will certify companies as HIPAA compliant, but their certification is not legally recognized as proof of compliance. 

there is no ‘safe harbor’ provision for the inclusion of protected health information in an application. Even if an application isn’t designed to collect or share personal health information the developer is still responsible for it if PHI makes its way into the application. 

## The Required Safeguards for Applications

HIPAA requires three types of data safeguards under the HIPAA Security Rule. These aren’t either/or. Applications subject to HIPAA oversight need to be compliant in all three areas: administrative, physical, and technical. 

Administrative safeguards refer to the documented policies, procedures, training, and operational roles that are documented and maintained to limit access to protected health information only to essential staff. 

Physical safeguards are the data protection measures that limit access to hosting facilities, racks and servers, as well as mandate the data redundancy and media destruction required to ensure access and protection of PHI. A HIPAA compliant hosting provider usually covers these requirements.

Technical safeguards are the application-specific measures that developers will most likely deal with. They include things like data encryption and decryption, logging and data audits, user authentication, data transmission integrity and more.

## Things to Consider When Developing for HealthKit

The very first thing is to determine whether the application will or may eventually collect or share PHI. Remember, apps can collect consumer health information and not require HIPAA compliance. It’s only when PHI will be shared with a covered entity that it becomes subject to HIPAA compliance. 

* Types of health data: no need to compliant to HIPAA for calory tracker and pedometer data, but glucose level has to be HIPAA compliant.
* Messaging application sending and receiving any user's PHI 
* iOS notifications and user communication: don’t publish PHI to push notifications, email, and SMS.
* Never share PHI with HIPAA non-compliant applications.
* High availability and redundancy
* Remote data management: Can the app wipe PHI from local storage on the phone in case the phone is lost?
* Even if the application does handle PHI, not all of the data needs to be stored in a HIPAA compliant environment. PHI can be sent to and stored with a compliant host, while non-PHI data is managed in a traditional application database.
* simply using a HIPAA compliant hosting provider for the application data does not make a HealthKit-enabled application HIPAA compliant.


[Resources for Mobile Health Apps Developers](https://www.hhs.gov/hipaa/for-professionals/special-topics/health-apps/index.html)
