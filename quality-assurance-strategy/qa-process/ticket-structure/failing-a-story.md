# failing a story

When failing a story, the same structure as raising a bug can be followed. The key difference is detailing what acceptance criteria or acceptance tests have failed.

For example:

* A summary of what was tested and what has passed on this test run
* A summary of what failed e.g. acceptance test \#3 failed on the 'THEN' statement
  * Describe what you encountered vs the expected outcome in detail \(screenshots/video recording etc\)
* URL / Browser / Devices tests were run on and which ones it failed on
* Severity
* Assignee

Note: It may be worth raising lowest severity/priority issues separately. For example, if there are small design issues that don't affect functionality, need to be fixed but only relate to a certain device, this can be raised as a separate bug to reduce the back and forth between stories and potentially be picked up in a front end design bug fixing period. The main bulk of the story can be UAT'd instead of waiting on a minor fix \(which can still go through UAT later on\).

See [creating a ticket from testing for more info on how to raise a bug](https://app.gitbook.com/@equalcare/s/the-platform/~/drafts/-MRdmcYwbg_Y95-bu7Rz/quality-assurance-strategy/qa-process/ticket-structure/creating-a-ticket-from-testing)



\*\*\*\*

