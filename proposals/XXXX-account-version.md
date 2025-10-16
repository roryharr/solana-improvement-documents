simd	title	authors	category	type	status	created	feature	supersedes	superseded-by	extends
XXXX
Title of SIMD. This should be concise and descriptive.
- Rory Harris
- Igor Durovic
Standard
Core
Idea/Review
2025-10-17
(fill in with feature key and github tracking issues once accepted)
Summary
Add Versioning to Account Information 

Motivation
Account information included in the LTHash cannot be updated as the old account hash needs to be deterministically mixed out. If an accounts hash other than the original was mixed out, it would become difficult to recreate the lattice hash to verify the accounts hash. Future SIMDs are planning on changing this information but there is no method at this time. 


Dependencies (Optional)
Lt Hash

SIMD-XXXX: Title of SIMD

A brief summary of the reason for the dependency

New Terminology
Accounts Version

Detailed Design
Explain the feature as if it was already implemented and you're explaining it to another Solana core contributor. The generally means:

Explain the proposed change and how it works
Where the feature fits in to the runtime, core, or relevant sub-system
How this feature was/could be implemented
Interaction with other features
Edge cases
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119 and RFC 8174.

Alternatives Considered
- Recalculating the LT Hash w
  Con: Rollout will be difficult for any changes. 

Impact
Account Information returned by RPC should be updated to include the version 
How will the implemented proposal impacts dapp developers, validators, and core contributors?

Security Considerations
N/A

Backwards Compatibility (Optional)
Updates LT Hash
Changes defi
