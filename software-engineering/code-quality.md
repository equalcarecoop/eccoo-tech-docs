# code quality

* Use and application of TDD \(Test-Driven Development\) within the development cycle. The benefit of TDD lies in using tests to specify software behaviour at a fairly low level, and automating these tests. This reduces the cost of validation and protects from reintroducing errors that have been fixed or inadvertently breaking something. This means that any failures at the QA stage can be codified, resubmitted to development and demonstrated to be resolved.
* Application of [BDD \(Behaviour-Driven Development\)](https://en.wikipedia.org/wiki/Behavior-driven_development) \(TDD at a macro level\) to build a shared understanding of user needs.
* Use of accessibility testing as part of end to end testing to pick up potential issues early. [Guidance](https://www.gov.uk/service-manual/helping-people-to-use-your-service/testing-for-accessibility) from GOV.UK useful. \(See also GDS's [audit of accessibility tools](https://alphagov.github.io/accessibility-tool-audit/)\). Initial automated testing makes use of [aXe](https://www.deque.com/axe/) and [Lighthouse](https://developers.google.com/web/tools/lighthouse/).

