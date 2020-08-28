# [⏎](README.md#Roadmap) KIP_23
> Upsert Code of Conduct (Proposal)

The Code of Conduct or SLA (Service-level agreement) is a text document (markdown) containing expected off-chain and on-chain behavior of all network actors.

By curation of the Code of Conduct (on-chain SLA) governance of Kira can transparently define its own rules, vision and processes used to effectively achieve consensus. In the result users can trust the network and understand how to become a network actor such as a validator or councilor.

## Upsert Code of Conduct

By submitting `upsert_sla` a proposal should be created that will enable governance set to update **Code of Conduct**. The upsert SLA function should have an assigned identifier in the functions registry.

_OPTIONALLY: It should be possible to define execution cost in genesis  - [Execution Fee](/spec/fees.md) to submit `upsert_sla` proposal._

Proposal should have following properties:
* Configurable in genesis `expiration` time (uint32) - seconds since submission
* Configurable in genesis `enactment` time (uint32) - seconds since expiration
* Allowed vote types: `yes`, `no`, `veto`, `abstain`
* ZIP compressed text content (data) up to 1 MB
* Status with following types:
  * `undefined` - 0x00
  * `active` - 0x01
  * `rejected` - 0x02
  * `passed` - 0x03
  * `enacted` - 0x04

_NOTE: Network actors with assumed roles `councilor` should by default posses ability to propose and vote on `upsert_sla`. Network actors with assumed roles `validator` should by default posses ability to vote on `upsert_sla`. Those types of permissions should be predefined in genesis_

## Proposal Vote

By submitting `vote` transaction along proposal identifier it should be possible for the governance members with the whitelisted permission to vote on `upsert_sla` to submit relevant vote types to pass or reject action of upserting Code of Conduct.




