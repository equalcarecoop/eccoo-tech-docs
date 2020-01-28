# audit

The audit component is responsible for recording critical information about data access and \(in the future\) other important business events.

## Critical Requirements

* Must record the date of the event
* Must record the identity of users accessing details
* Must record the reference of the data being accessed
* Should record the action being taken on the record \(view, update, etc\)
* Must **not** record the content of the data accessed
* Could be non-repudiable to avoid tampering with the access log
* Should meet the demands of GDPR

## Implementation

This is essentially a transaction log. The API should be 'append only' POSTing events to a restful endpoint. A separate query interface should enable listing events filtered by date.

In simple terms, this may be a centralised logger which enables API layers to track data access. A platform such as [Nagios](https://www.nagios.com) or [Graylog](https://www.graylog.org/) could be configured to manage this task, although may be limited as a trusted source of audit data.

This could also be an application for a ledger. Commiting business critical events to a ledger would provide demonstration that it had not been tampered with.

