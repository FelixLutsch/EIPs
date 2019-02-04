---
cip: <to be assigned>
title: Whitelisting
author: <Felix Lutsch (felix@chorus.one), Brian Fabian Crain (brian@chorus.one)>
discussions-to: <URL>
status: Draft
type: <Meta>
created: <2019-02-04>
---

<!--You can leave these HTML comments in your merged CIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new CIPs. Note that an CIP number will be assigned by an editor. When opening a pull request to submit your CIP, please use an abbreviated title in the filename, `eip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Provide a simplified and layman-accessible explanation of the CIP.-->
This CIP introduces the concept of whitelisting and presents a possible implementation. Whitelisting is based on the idea that a validator in the Cosmos Network should have the ability to restrict who is delegating to them by maintaining a list of public keys (the whitelist).

## Abstract
<!--A short (~200 word) description of the technical issue being addressed.-->
The current delegation specification doesn't allow validators to restrict who bonds Atoms with them. The delegation function only looks to see if a validator is currently bonded or not. The function then assigns the delegated Atoms to the stake of that validator, provided the validator of choice is in the active validator set and his status is not currently revoked. The following feature request would introduce a check that queries whether the delegation address is part of the whitelist maintained by the validator before allowing delegation. It also specifies a potential treatement for existing delegations that are not part of this whitelist.

## Motivation
<!--The motivation is critical for CIPs that want to change the Cosmos protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the CIP solves. CIP submissions without sufficient motivation may be rejected outright.-->
This feature is required to allow validators to comply with regulations in their respective jurisdictions. A Cosmos Hub validator is providing a service to delegators: running the infrastructure to participate in consensus on the Cosmos Hub in exchange for a share of the rewards paid out by the protocol. Without whitelisting a validator is unable to ensure that a delegator agreed to their terms of service. Additionally, a validator does not have any option to exclude delegators that do not comply with the governing law in their jurisdiction (e.g. KYC/AML requirements).

## Specification
<!--The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).-->
A draft of a possible implementation can be found [here](https://docs.google.com/presentation/d/1yeRxFs_BaKyHOMzIXRKQiIX9qZXdQ0R04_4nvKJGn7o/edit#slide=id.p2).

## Rationale
<!--The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->
The rationale for this feature request is laid out in full detail [here](https://docs.google.com/document/d/1CEfwTyJQPlapOajBo4vYAWklWbm7xuNTtJRQZlQjPDA/edit?ts=5b056c4a). There is wide support for such a feature within the validator community. (OTHER PULL REQUESTS, EVIDENCE?) https://github.com/cosmos/cosmos-sdk/issues/3290

## Implementation
<!--The implementations must be completed before any CIP is given status "Final", but it need not be completed before the CIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.-->
Actual implementation to be discussed

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
