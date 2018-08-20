<pre>
  DIP: 00XX
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
3.  [MNO Polls](#mno-polls)
4.  [RFP System](#rfp-system)
5.  [Modified Trigger Gobjects](#modified-trigger-gobjects)
5.  [Approval and Implementation](#approval-and-implementation)
6.  [Copyright](#copyright)

## Abstract

This DIP introduces new `gobject` types. The first, `type: 4` (2 Dash submission Fee), is an 'MNO poll', in which you could poll MNO and get a consensus with a slightly lower barrier to entry than today. The second, `type: 5` (1 Dash submission Fee), is a novel new `gobject` type that is part of a larger goal of delivering a Treasury system that improves efficiency with funding by enabling a free market with competition between potential contractors, as well as funding projects that MNO have prioritized rather than just whatever gets submitted each month.

## Motivation

While developing Dash Nexus we came to the conclusion that in order to support further improvements to governance and funding inside of the Dash ecosystem, we need to improve the underlying protocol. This is the first of many steps on that journey and requires some changes to the `gobject` code which would implement additional Governance Object types, enabling the system to further scale and support a wider range of governance operations and ultimately increase efficiency for MNO evaluation, improve verbosity inside of the somewhat opaque Governance system, and ultimately increase the capabilities of Decentralized Governance By Blockchain.


## MNO Polls

(Could also call them Non-Binding Referendums)

There's a lack of good mechanisms for getting feedback from MNO on decisions around protocol changes and organizational decision-making that can be simplified and better scaled by the introduction of a Governance Objects designed purely with getting an MNO conesus on non-funding topics.

The lifecycle on MNO polls should be set to two weeks (8,308 blocks), rather than the usual 30 Days, in order to arrive at consensus around key issues much more rapidly.

### Spam Reduction Option 1

One way to keep spam to a minimum here is charging 2 Dash for the submission of a MNO Poll. This would allow anyone to submit a proposal but it may not be enough of a deterrent to prevent bad actors from trolling the system.

### Spam Reduction Option 2

Another suggestion I received was to require that a new MNO Poll `gobject` used the parent hash from a proposal which had passed in a previous cycle. This would limit the number of individuals who could poll the network, but it would also do a great job of preventing spam because only "trusted" contractors could submit questions.

### How to achieve finality?

We propose introducing another `trigger`-like `gobject` for handling finality and consensus here. (Can be much improved with DashDrive)


## RFP System

The RFP system has a number of components and will need to be supported by both the protocol back-end as well as with some new front-end interfaces on Dash Nexus.

RFP Flow:

1. User has an idea for something they think would improve the network
2. User thinks that it's worth the 2 Dash to find out if other MNO agree
3. User submits that idea for an RFP through Dash Nexus which wraps up the `gobject prepare` and `gobject submit` commands within its slick interface
4. MNO's vote YES and NO on the currently valid RFPs to rank their importance
5. The top-ranked RFPs are added to a new `trigger`-like `gobject` which is purely for the sake of finality and consensus. There could be multiple active triggers at once since it's probably easiser to generate one for each `gobject` above the threshold which preserves its validity beyond the current voting tally. (Can be much improved with DashDrive)
6. Potential contractors begin to submit proposals of `type` 6  which reference the RFP `gobject` as a parent object. Only proposals represented within a currently valid parent `gobject trigger` are valid and accepted.
7. Masternodes vote on the different `type` 6 `gobjects` and whichever one ends up with the most votes is selected for funding in a special `trigger` and subsequently, a special `superblock`.
8. Sentinel then begins marking that RFP as expired because the RFP loop has been closed. It also begins marking the additional `type` 6 `gobjects` as expired and begins purging their votes.
9. Project is completed with the best possible outcome.


TODO:
Think about how Escrow would fit into this.


## Modified Trigger Gobjects

Both the RFP system and the MNO Polls require a small modification to the `trigger` object type (or introduction of a new one) in order to enable the functionality required for MNO Polls and RFPs.


TODO:
Look into the trigger gobject to see if all the fields are required or not, for example we don't need a payment address or payment amount. We also don't want to prune them or even really have Sentinel interact with them except in terms of providng the consensus mechanism for finality and deterministic creation of the `trigger` object.


## Approval and Implementation

Prior to merging any code for this into the `master` branch. A governance proposal should be submitted to the network and must reach the minimum quorum before these changes to critical governance functionality are approved by the key stakeholders.


## Copyright

Copyright (c) 2018 Jeff Hodges. [Licensed under MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2017 Dash Core Team.  [Licensed under MIT License](https://opensource.org/licenses/MIT)
