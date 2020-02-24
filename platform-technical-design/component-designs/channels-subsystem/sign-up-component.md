# sign-up

The sign-up component is a process manager responsible for interacting with the core components within the system to establish a new user of the system.

## C​ritical requirements

The sign-up process

* must manage the process of basic sign-up as a user of the platform
* must collect required customer data
* must set up all required records and authorisations within the platform
* should follow the design outlined in the [previous service design work](https://app.asana.com/0/1141006338993484/1141006338993484), extending / challenging it where sensible
* won't differentiate between care givers and care receivers - this is the role of 'hat selection'. This is important, as it reinforces the lack of differentiation between users of the platform.

## ​Implementation

This will initially be implemented as a series of web forms having a close alignment with the Identity and Access Management components. For the MVP at least, it may use lightly customised versions of the out-of-the-box functionality of the chosen IAM component. This means that we may have slightly less control over the exact look and feel of the signup, at the expense of getting something up and running fast. This will need to be looked at in the context of the delivery priorities.

