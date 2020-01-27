# matching

Service to perform match between care giver with specific needs and care receiver. Based on algorithm that uses the graph and individual profiles to propose appropriate relationships between people.

The details of the algorithm are as yet undefined, but are assumed to require the following types of information

* Care receiver location
* Care receiver needs
* Care receiver preferences
* Care giver location
* Care giver capabilites
* Care giver demographic information

It is suggested that an initial implemention of the matching component errs on the side of simplicity: location, needs/capabilities.

## Critical requirements

* Must accept a request for matching
* Must present a list of potential matches
* Should accept additional constraints
* Should report on matches made for demographic purposes

## Implementation

The implementation of Matching will rely heavily on information stored in the relationships component. The initial implementation may be simply a query against the graph. As the algorithm is fine tuned, the core could replaced by AI techniques such as Machine Learning \(using user feedback to improve future matches\).

