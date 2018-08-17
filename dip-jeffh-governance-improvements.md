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
3.  [MNO Poll](#mno-poll)
4.  [RFP System](#rfp-system)
5.  [Approval and Implementation](#approval-and-implementation)
6.  [Copyright](#copyright)

## Abstract

This DIP introduces new `gobject` types. The first, `type: 4` (2 Dash Fee), is an 'MNO poll', in which you could poll MNO and get a consensus with a slightly lower barrier to entry than today. The second, `type: 5` (1 Dash Fee), is a novel new `gobject` type that is part of a larger goal of delivering a Treasury system that improves efficiency with funding by enabling a free market with competition between potential contractors, as well as funding projects that MNO have prioritized rather than just whatever gets submitted each month.

## Motivation

While developing Dash Nexus we came to the conclusion that in order to support further improvements to governance and funding inside of the Dash ecosystem, we need to improve the underlying protocol. This is the first of many steps on that journey and requires some fundamental changes to the `gobject` code which would implement additional Governance Object types, enabling the system to further scale and support a wider range of governance operations and ultimately increase efficiency for MNO evaluation, improve verbosity inside of the somewhat opaque Governance system, and ultimately increase the capabilities of Decentralized Governance By Blockchain.


## MNO Polls

There's a lack of good mechanisms for getting feedback from MNO on decisions around protocol changes and organizational decision-making that can be simplified and better scaled by the introduction of a Governance Objects designed purely with getting an MNO conesus on non-funding topics.

The lifecycle on MNO pools should be two weeks, rather than the usual 30 Days, in order to 

???

How to achieve finality and store results on the blockchain. Could be done either with `OP_RETURN` (no great), or potentially by taking advantage of the `revision` field in `gobjects`.


## RFP System

The RFP system has a number of components and will need to be supported by both the protocol back-end as well as with some new front-end interfaces on Dash Nexus.

RFP Flow:

1. User has an idea for something they think would improve the network
2. User thinks that it's worth the 2 Dash to find out if other MNO agree
3. User submits that idea for an RFP through Dash Nexus which wraps up the `gobject prepare` and `gobject submit` commands within its slick interface
4. MNO's vote YES and NO on the currently valid RFPs
5. The top-ranked RFPs are selected for 


## Approval and Implementation

Prior to merging any code for this into the `master` branch. A governance proposal should be submitted to the network and must reach the minimum quorum before these changes to critical governance functionality are approved by the key stakeholders.


## Copyright

Copyright (c) 2017 Dash Core Team.  [Licensed under MIT License](https://opensource.org/licenses/MIT)
