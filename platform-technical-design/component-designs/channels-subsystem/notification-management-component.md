# notifications

The notification component is responsible for transmission of notifications to platform users via their preferred mechanism. To support this, it also managed contact details \(e.g. email addresses, mobile phone numbers\) as well as preferred contact mechanism \(e.g. email, SMS\).

## Critical requirements

The notifications component

* must record users contact details
* must record users contact preferences
* must send notifications via the selected contact mechanism based on 

## Implementation

UX design is required around this component to map the types of notifications and ways of selecting preferences.

Sending the notifications should be delegated to a service such as [OneSignal](https://onesignal.com/).

