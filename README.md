# PLEBNET for plebs

## Getting Started

You need a [Lightning Network](https://en.wikipedia.org/wiki/Lightning_Network/) node and [Telegram](https://telegram.org/) in order join [PLEBNET](http://kycjelly.com).

### Node

There's several newbie options for getting a Lightning node set up and running.

* [BTC SESSIONS](https://youtu.be/fppmhqjqh2E) has a good video walkthrough for getting started with Raspberry Pi and Umbrel
* [Umbrel](https://getumbrel.com/) is a newbie-friendly package that runs on Raspberry Pi v4+
* [RaspbiBlitz](https://github.com/rootzoll/raspiblitz) is another option for Raspberry Pi
* [Start9](https://start9.com/) is an all-in-one option that includes the necessary hardware
* [myNode](https://www.mynodebtc.com/) is another all-in-one with hardware
* [RaspiBolt](https://stadicus.github.io/RaspiBolt/) has some good information on how to set up the necessary services manually

### Telegram

PLEBNET discussion and coordination happens on the Telegram chat platform.

Download the [Telegram app](https://telegram.org/) and join the [PLEBNET](http://kycjelly.com) group.

### CheeseRobot ₿

A Telegram bot that will allow you to join and interact with the PLEBNET. 

You'll want to send a message to `@cheeserobot` to claim and add your node. Start with `/claim` and follow the instructions to get add your node id. Then, in the PLEBNET channel, use `/id@cheeserobot` to get yourself added to the graph.

## Opening Channels

### Add Liquidity

Generate a Lightning wallet and add some funds so that you can open channels. Keep in mind that PLEBNET prefers [girthy channels](#keep-it-girthy), so fund your node accordingly.

### Find nodes in PLEBNET Telegram group

You'll need to find some other nodes in PLEBNET to open channels with.

Typing `/groupnodes@cheeserobot` will output a list of the 50 most recent members and nodes. `/graph@cheeserobot group` will generate and show a visual graph of all of the connected nodes in PLEBNET. You can contact plebs on this list and see if they'd like to open a channel.

You can also just ask in the PLEBNET channel if anyone is interested in opening a channel with you.

### Keep It Girthy

It's best to have fewer big channels with more sats than it is to have many smaller ones. The recommended minimum channel size is 2 million sats, which would be 1 million per node on the channel.

### Balanced Channels

The idea is to have balanced channels. This means that there is an equal amount of sats between each node on the channel. 

For example, if `Node A` opens a channel with `Node B` for 2m sats, it will start entirely on their end. `Node A` will want to find a way to have 1m sats on each side of the channel.

There are several different ways to accomplish this.

#### "Ghetto Submarine Swap"

**ONLY DO THIS WITH ESTABLISHED AND TRUSTED PLEBNET NODES! IT IS POSSIBLE TO LOSE SATS DOING THIS.**

1. `Node A` opens a channel with X sats
2. `Node B` sends a Lightning invoice for half of the amount X sats that was opened on the channel
3. The `Node A` operator sends the address of their preferred on-chain Bitcoin wallet to the operator of `Node B`
4. The `Node B` operator sends half of the amount X sats of the opened channel to the Bitcoin wallet of the operator of `Node A` from step 3
5. `Node A` pays the Lightning invoice
