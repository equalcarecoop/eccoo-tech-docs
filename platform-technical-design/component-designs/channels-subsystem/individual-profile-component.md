# individual profile

The individual profile is the primary means that platform users will use to interact with the platform. 

## Critical requirements

The individual profile:

* must ensure that the platform user is authenticated \(i.e. logged in\) before accessing the profile
* must present only the features that the platform user is allowed to see, based on their roles
* should deploy a consistent design language in presenting choices \(this is more of a UX concern, but added here as a cross reference\)
* must not include any administrative features. This must be as separate channel, due to the danger of data and function leakage.

The initial feature set will be subject to UX design, but could cover:

* Profile / hat selection - from an initial list of care giver, care receiver, care arranger \(i.e. relative\)
* Care matching search - initiated by care receiver?
* Recording of appointment arrangements made outside the platform \(e.g. via phone / email\)
* Adding case notes
* Confirming completion of appointment / care interaction
* Taking payment from care receivers / care arrangers \(probably handing off to payment platform\)
* Listing completed care interactions

## Implementation

This channel will be a web-based platform for the MVP. Ultimately, some of the features available via this channel will be available by other channels such as voice.

The design of the individual profile will be driven by the UX work.

It may be that this single channel is actually multiple apps - one per feature. As a principle, any components should be designed and deployed in a modular manner to enable this refactoring and splitting. An initial split could be the relationship-focussed features \(matching, appointment arranging, care notes\) and the transaction / payment focussed features \(care 

