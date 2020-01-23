# matching

Preconditions:

* Care Receiver registered in system
* Care needs are captured (How???)

Scenario: Simple match

1. Care receiver requests a new caring relationship, providing subject PID and own credentials to the Matching UI
2. Matching component requests base person information from the individual profile component, based on credentials provided
3. Matching component performs one or more queries to retrieve potential care givers from relationships component
4. Matching component assesses the potential matches and orders according to 'The Algorithm'
5. Matching component presents the ordered set of matches via the Matching UI

