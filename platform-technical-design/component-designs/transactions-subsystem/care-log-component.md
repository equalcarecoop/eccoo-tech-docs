# care log

Care logging is the record of caring interactions that have taken place, and captures the transfer of value enabled by the platform. It is the other half of the platform core along with the [relationships](../relationships-subsystem/relationship-component.md) component.

## Critical requirements

The care logging component

* must enable users to confirm that the care log record is correct
* must enable users to confirm the care log record with adjustments (e.g. to time)
* must store an immutable and non-repudiable record of the care log (i.e. unchangeable and tamper-proof and therefore trustworthy)
* could (subject to UX design) progress between pending and confirmed state based on a timer (i.e. assume agreement if not confirmed within a period of time)
* should facilitate the 'eccoo transaction fee' (?)
* won't manage disputes between platform users

## Implementation

This is a strong candidate for implementation as a distributed ledger (blockchain).

The transaction model implemented in the technology is shown in the diagram below.

![State model for the care logging transaction](<../../../.gitbook/assets/Ledger State Transitions.png>)

Ultimately, post MVP, this will extend to cover the full scope of required functionality - e.g. include moving from 'pending' to 'dispute' state in the event of disagreement between care giver and care receiver.

Required API:

* Register care transaction
* Confirm care transaction

