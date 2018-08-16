<pre>
  DIP: 000?
  Title: Extended Governance Object Types
  Author: Jeff Hodges &lt;jeff@jeffhq.com&gt;
  Comments-Summary: No comments yet.
  Status: Draft
  Type: Standard
  Created: 2018-08-16
  License: MIT License
</pre>

## Table of Contents

1.  [Abstract](#abstract)
2.  [Motivation](#motivation)
3.  [Conventions](#conventions)
4.  [Copyright](#copyright)

## Abstract

This DIP introduces new `gobject` types. The first, `type: 2` (2 Dash Fee), is a PURE governance proposal, in which you could poll MNO and get a consensus with a slightly lower barrier to entry than today. The second, `type: 3` (1 Dash Fee), is a novel new `gobject` type that is part of a larger goal of delivering a Treasury system that increases competition among contractors in order to get a stronger free market (needs competition), and only funds projects that MNO have prioritized. 

## Motivation

While developing Dash Nexus we came to the conclusion that in order to support further improvements to governance and funding inside of the Dash ecosystem, we need to improve the underlying protocol. This is the first of many steps on that journey and requires some fundamental changes to the `gobject` code which would implement additional Governance Object types, enabling the system to further scale and support a wider range of governance operations and ultimately increase efficiency for MNO evaluation, improve verbosity inside of the somewhat opaque Governance system, and ultimately increase the capabilities of Decentralized Governance By Blockchain.

## RFP System

* `0x20000000` is the bit sequence `00100000000000000000000000000000` and is the current version of dash blocks.
* `0x20000002` is the version used to signal acceptance of a consensus change rule.
A miner should use this version to signal acceptance of the miner and the masternode for the block of a consensus rule change.
* We use `%` as it is used in C++. It is the remainder on division. So `7 % 3` is 7 modulo 3 and is equal to 1.


## Consensus Protocol Changes

Currently there is a protocol rule as follows:
* A block over 1MB is invalid.

To allow the network to scale we replace this rule with the two rules:
* A block over 2MB is invalid.
* A block with at least one transaction over 100kB is invalid.

Note the 100kB cap on transaction size will not necessarily be satisfied by old blocks.
For this reason this new rule must only be enforced on blocks after activation of the protocol change.


## Copyright

Copyright (c) 2017 Dash Core Team.  [Licensed under MIT License](https://opensource.org/licenses/MIT)
