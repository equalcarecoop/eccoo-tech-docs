# transactions subsystem

This subsystem collects a series of components which underpin the transfer of value across the platform. The value exchanged could be in the form of:

* paid caregiving appointments
* financial payments
* ad-hoc volunteer social calls

Each of these describes the platform economy, and needs to be underpinned by a trustworthy ledger. This is a potential application of blockchain-type technologies.

Although the initial MVP implementation will likely be a simple network, it is possible that as the platform grows there will be a need to distribute transactions across a network. The power of a distributed ledger database network \(a.k.a. blockchain\) is that it radically decentralises the data storage, underpinning trust through exchange of encrypted data.

## Candidate technologies

The database technology underpinning the transactions subsystem

* must be able to robustly model state changes
* must increase trust by ensuring the transactions are immutable \(unchangeable\) and non-repudiable \(tamper-proof\)

This set of requirements points towards a Ledger Database, a class of databases that includes blockchains.

The following provides a good overview of RDBMS, NoSQL, Ledger DB.

{% embed url="https://hackernoon.com/relational-nosql-ledger-databases-work-not-permissioned-blockchains-9ccaef7b3139" caption="" %}

One of the most popular permissioned blockchains is [Hyperledger Fabric](https://www.hyperledger.org/projects/fabric).

