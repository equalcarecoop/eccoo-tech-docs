---
description: workflow and strategy for manual testing
---

# manual testing

There will be 2 phases to the manual testing and reporting process:

## Before build

Before dev starts working on a ticket that would be due for manual testing, there should be a brief communication between dev and QA to discuss the specification of the ticket so that QA can outline the test basis and design the tests - this will enable QA to complete the testing faster as they would be able to prepare for testing whilst the build is in progress.



## After build

1. To submit a ticket for manual testing a member of dev will move their ticket the`QA manual testing` column in Asana once they have finished their work on it.
2. Tests will be executed and reports created.&#x20;
3. Ticket updated with a brief summary of the results e.g. coverage, pass/fail rate and any comments. Link will be provided to the test suite should anyone need more information.&#x20;
4. Ticket is discussed in daily scrum and we will decide whether ticket has passed or if due to a few bugs if it needs to return to dev.&#x20;
5. why did it fail? defect? lack of clarity in specification or other



### Responsiveness & browser compatibility

Manual testing will be conducted in the following scenarios to ensure that users are receiving the same experience (as intended) of the web app regardless of operating system, device or browser:\
\
**Computer:**\
Mac OS 11.2: Safari, Chrome\
Ubuntu 20.04: Firefox\
Windows 10 VM: Edge, IE.\
\
**Tablet:**\
Windows tablet: Edge, IE.\
\
**Mobile:**\
Android 10: Chrome, Firefox.\
iOS 14: Safari, Chrome.\




