# care notes

The care notes component is responsible for tracking notes associated with a care receiver's care. Conceptually, it is a shared notebook with multiple entries created by and visible to the care receiver, care givers and other interested parties such as family members.

## Critical Requirements

* It should be possible to limit the readership for individual entries
* It must be possible to protect the sensitive personal data in the event of data breach - encryption

## Implementation

This could be implemented as a NoSQL database with the following structure.

```yaml
crid: care receiver ID - reference to recipent of care
date: timestamp for entry
visibility: permissions required to view read
note: formatted care note
```