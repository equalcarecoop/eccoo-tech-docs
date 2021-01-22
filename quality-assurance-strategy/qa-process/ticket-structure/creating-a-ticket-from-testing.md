# creating a ticket from testing



Bugs, Questions and Change Requests can be raised at any time.

* Bug \(a defect against expected behaviour\)
* Change Request \(for a new feature\)
* Question \(for a question that may require group discussion\)

The following outlines how to raise a **bug** that is not covered by acceptance criteria on a story.

**Summary**

Add a quick summary that allows us to identify the bug easily in Jira

Example: ‘Submit button not working’  
  
**Description**

This needs to cover:

* How the bug can be recreated with test steps \(ideally with GIVEN, WHEN, THEN scenarios\)
* What the ‘desired behaviour’ is \(i.e. what should actually happen\)
* What environment and device the bug occurred in \(URL, operating system, browser version\)
* Any screenshots or video recordings that can help reproduce or identify the issue easily

Example: ‘On the homepage under the signup for newsletter section the button is not working’. 

A user can enter their email address in the field but when the submit button is clicked there is no response message and they are not added to the newsletter list. 

Steps to reproduce:

* GIVEN I am on the newsletter page
* AND I enter valid details for the newsletter sign up
* WHEN I click submit on the newsletter sign up
* THEN no action occurs

\[Screenshot\]

Expected functionality: The button should submit with a ‘thank you’ response message being displayed and the user being added to the Mailchimp list. 

Tested on: \[URL\]

Device: \[iPhone / iOS 14 / Safari\] OR \[All Devices\]

**Severity Levels**

Using 3 levels for simplicity:

* High

  * The defect affects critical/major functionality or major data. It does not have any obvious work around and is unsuccessful in it's function.
  * Example: A feature is not functional from one module 

* Medium

  * The defect affects minor functionality or non-critical data. It is not desirable and may have a workaround.
  * Example: A feature that is not functional in one module but the same task is doable from another module.

* Low
  * The defect does not affect functionality or data. It does not even need a workaround. It does not impact productivity or efficiency. It is merely an inconvenience.
  * Example: Layout discrepancies, spelling/grammatical errors.

  
**Assignee**

Assign the issue to the developer who it relates to.



Note: priority of tickets should also be taken into account and can be set when discussing the issues.





