---
simd: 'XXXX'
title: Add Version to Account
authors:
  - Rory Harris
category: Standard
type: Core
status: Idea
created: 2025-10-20
feature:
supersedes:
superseded-by:
extends:
---

## Summary
Add account version field to the account stored meta and include the account version field in accounts hash. 

## Motivation
There are two main motivations: Updating the meta data stored for an account in the snapshot, and updating the data included in the accounts hash. Currently the accounts database has a static header of 136 bytes along with any data stored in the account. 40 bytes of this data has been deprecated and is guaranteed to be zero. With a new version of an account, this data could be removed, shrinking the minimum account size by 40 bytes, which could result in a net reduction of 40GB to the accounts database size. In addition future SIMDS may change the data stored in the account, and/or the data included in the acccounts hash. By including a version, the correct initial hash can be calculated, and mixed out frmo the lattice hash before hte new hash is mixed in.


## New Terminology
Account Metadata Version - Tbe version of the account. 

## Detailed Design
StoredMeta currently has an obsolete field: write_version_obsolete. The lowest 4 bits of this should be repu

Explain the feature as if it was already implemented and you're explaining it to another Solana core contributor. The generally means:

## Explain the proposed change and how it works
Where the feature fits in to the runtime, core, or relevant sub-system
How this feature was/could be implemented
Interaction with other features
Edge cases
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119 and RFC 8174.

## Alternatives Considered
- Recalculating the LT Hash w
  Con: Rollout will be difficult for any changes. 

## Impact
Account Information returned by RPC should be updated to include the version 
How will the implemented proposal impacts dapp developers, validators, and core contributors?

## Security Considerations
N/A

## Backwards Compatibility (Optional)
Updates LT Hash
Changes defi
