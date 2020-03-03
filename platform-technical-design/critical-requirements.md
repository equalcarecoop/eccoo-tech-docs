---
description: >-
  This section outlines the high-level requirements that must be met by the
  system
---

# critical requirements

## Features

A prioritised set of features is outlined in the [Strategic Product Planning](https://app.asana.com/0/1150454752566641/board) board.

## Quality attributes

This section outlines the quality \(rather than functional\) characteristics that the platform must meet.

### Accessibility

The UI components must be designed to appropriate accessibility standards. At a minimum, this must include:

* W3C [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/) for Web Content - up to AAA level where appropriate
* W3C [WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) for Dynamic Web Apps

There are excellent resources available at the [W3C Web Accessibility Initiative page](https://www.w3.org/WAI/).

The system should support users with complex needs. Hyper-accessibility.

References:

* [https://alistapart.com/article/standards-for-writing-accessibly/](https://alistapart.com/article/standards-for-writing-accessibly/)

### Internationalisation \(i18n\) and Localisation \(l10n\)

The platform may ultimately be used in multiple countries: as such, all platform components should be internationalised so that they can be easily localised.

[https://en.wikipedia.org/wiki/Internationalization\_and\_localization](https://en.wikipedia.org/wiki/Internationalization_and_localization)

### Audit

* All access to data should be logged for later querying.
* NOTES... Must cover CQC etc

### Privacy

The system should adhere to the principles of GDPR legislation as enshrined in the [DPA 2018](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/).

### Security

* All data at rest must be encrypted
* Sensitive personal information must be encrypted at field level
* The system must enforce access control over secure data

### Scalability

It should be possible to scale the system as load increases.

Data stores should be scalable horizontally \(e.g. by sharding\) rather than just vertically \(i.e. by adding more CPU and memory\).

### Portability

The system must not be tied in to a given hosting platform, using proprietary technologies.

Technologies chosen should either be open source or commodities adopting open standards.

### Availability and Recovery

We are building a system that could be used 24 hours per day, so we aim for no unplanned downtime. There is an expectation that the system must be reliable, and in the event of a failure it can be recovered quickly. We aim for in excess of 99% up time, with no more than 2 outages per month. This would equate to 2 outages of up to 4 hours each.

Recovery objectives, in the event of catastrophic failure:

* Recovery Point Objective: No loss of committed transactions in the event of infrastructure failure
* Recovery Time Objective: Recreation of state within 4 hours in the event of infrastructure failure

A consistently updated risk log detailed known and predictable issues along with mitigation plans.





