---
date: 2018-09-21T21:07:13+01:00
title: DIP Documentation
weight: 100
type: index
---

## Dash Improvement Proposals (DIPs)

DIP stands for Dash Improvement Proposal. Similar to Bitcoin's [BIPs](https://github.com/bitcoin/bips/), a DIP is a design document providing information to the Dash community, or describing a new feature for Dash or its processes or environment. The DIP should provide a concise technical specification of the feature and a rationale for the feature.

Because Dash is forked from the Bitcoin codebase, many of the BIPs can be applied to Dash as well (a list of the BIPs updated to include Dash-specific details can be found [here](https://github.com/dashevo/bips)). The purpose of the DIPs is not to duplicate those which exist as BIPs, but to introduce protocol upgrades or feature specifications which are unique to Dash.


## Contributions

We use the same general guidelines for introducing a new DIP as specified in [BIP 2](https://github.com/bitcoin/bips/blob/master/bip-0002.mediawiki), with a few differences. Specifically:

* Instead of the BIP editor, initiate contact with the Dash Core development team and your request should be routed to the DIP editor(s). The DIP workflow mimics the BIP workflow.
* Recommended licenses include the MIT license
* Markdown format is the preferred format for DIPs
* Following a discussion, the proposal should be submitted to the DIPs git repository as a pull request. This draft must be written in BIP/DIP style as described in [BIP 2](https://github.com/bitcoin/bips/blob/master/bip-0002.mediawiki), and named with an alias such as "dip-johndoe-infinitedash" until the editor has assigned it a DIP number (authors MUST NOT self-assign DIP numbers).


## Dash Improvement Proposal Summary
Number | Layer | Title | Owner | Type | Status
--- | --- | --- | --- | --- | ---
[1](dips/dip-0001) | Consensus | Initial Scaling of the Network | Darren Tapp | Standard | Final
[2](dips/dip-0002) | Consensus | Special Transactions | Samuel Westrich, Alexander Block, Andy Freer | Standard | Proposed
[3](dips/dip-0003) | Consensus | Deterministic Masternode Lists | Samuel Westrich, Alexander Block, Andy Freer, Darren Tapp, Timothy Flynn, Udjinm6, Will Wray | Standard | Proposed
[4](dips/dip-0004) | Consensus | Simplified Verification of Deterministic Masternode Lists | Alexander Block, Samuel Westrich, UdjinM6, Andy Freer | Standard | Proposed
[5](dips/dip-0005) | Consensus | Blockchain Users | Alexander Block, Cofresi, Andy Freer, Nathan Marley, Anton Suprunchuk, Darren Tapp, Thephez, Udjinm6, Alex Werner, Samuel Westrich | Standard | Proposed
[6](dips/dip-0006) | Consensus | Long-Living Masternode Quorums | Alexander Block | Standard | Proposed
[7](dips/dip-0007) | Consensus | LLMQ Signing Requests / Sessions | Alexander Block | Standard | Proposed


## License

Unless otherwise specified, Dash Improvement Proposals (DIPs) are released under the terms of the MIT license. See [LICENSE](LICENSE) for more information or see https://opensource.org/licenses/MIT.