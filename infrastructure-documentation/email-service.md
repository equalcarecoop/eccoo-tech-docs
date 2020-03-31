# email service

We use Google GSuite as the main business email service.

## Email Security

We will comply with the [NHS Digital DCB1596 Secure Email](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dcb1596-secure-email) specifications. This requires that:

* Must implement anti-virus, anti-malware, anti-spam
* Must implement DMARC, initially in a quarantine mode, but with a timescale to move to blocking mode
* Must implement SPF, initially in a SOFTFAIL mode, but moving to FAIL
* Must use opportunistic TLS

It also recommends that

* Should implement MTA-STS
* Should implement TLS-RPT

We have implemented these in our DNS records, as evidenced on the [most recent Hardenize report](https://www.hardenize.com/report/equalcare.coop/1585665523). 





