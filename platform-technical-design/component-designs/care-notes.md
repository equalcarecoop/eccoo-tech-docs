# care notes

The care notes component is responsible for tracking notes associated with a care receiver's care. Conceptually, it is a shared notebook with multiple entries created by and visible to the care receiver, care givers and other interested parties such as family members.

## Critical Requirements

* It should be possible to limit the readership for individual entries
* It must be possible to protect the sensitive personal data in the event of data breach - encryption

## Implementation

This should be implemented as a NoSQL database with the following structure.

```json
{
  "pid": "112-121af123-a",
  "permissions": {},
  "timestamp": "20200101T103002Z",
  "notes": "Care note content."
}
```

* `pid` is the reference to the person identifier in the platform
* `permissions` is an object defining who can see and edit the note
* `timestamp` is an ISO 8901 formatted timestamp
* `notes` is a string containing the notes

The notes will need to be encrypted to prevent data loss.

The API for the service will need to enable the following actions:

* Create note for case
* Limit readership
* Retreive note for case
