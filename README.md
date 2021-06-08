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

You can go to [http://graph.kycjelly.com/](http://graph.kycjelly.com/) to see the current visual graph of nodes, or type `/graph@cheeserobot group` in the PLEBNET chat.  `/groupnodes@cheeserobot` will output a list of the 50 most recent members and nodes. You can contact plebs form the graph or list and see if they'd like to open a channel.

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

## Maintaining Proper Node Hygiene

### Keep Your Node Online

When you're running a lightning node, it's important to keep consistent uptime. This is good for you, your peers, and the overall community. Making sure your node stays online improves your reliability, as well as the reliabity of nodes that connect to you. If your node reboots or goes offline repeatedly, your reputation will be negatively impacted, and other peers will choose to route around you. If your node is offline for an extended period of time, you also run the risk of having your open channels force-closed, which can result in losing sats as the channel balance settles on-chain.

### Set a Static IP Address

One of the most important aspects to keeping your node online is setting a static IP address. Normally, your router assigns IP addresses dynamically to every device on the network. When the router refreshes its IP tables from time to time, some or all of the devices connected to it are reassigned new addresses. Generally, your devices will not alert you when this happens. Some models of wireless printers will display a message on the screen when the IP address changes, but by default, your laptop, smartphone, or node will not inform you when this happens. 

The solution for this is to change your router's settings to lock the IP address used by your node. Depending on the type of router you use, this might be referred to as a '''manually-assigned IP''', a '''reserved IP''', or you may need to simply turn off '''automatic IP''' assignment. You might have to look in the advanced settings section to find this feature. Once you've set the IP address, you shouldn't have to reboot your node, but if you do, it should retain the same IP address when it comes back up.

![Image](https://i.imgur.com/OwazT9K.jpeg)
Example of the Reserved IP settings screen on the Google Home app.

### Make Friends With Lightning Watch Bot

One simple way to be notified in the event your node becomes unavailable is to register it with @lightningwatchbot, a Telegram bot that will keep an eye on your node's up/down staus. Start a conversation with the bot, and it will walk you through the steps to connect your node. As a free service, it will send you alerts on a one hour delay. For a faster response time, you can open a channel of any size with the bot (a great way to practice opening channels) and send it a small payment to receive notifications for your desired duration. 

![Image](https://i.imgur.com/voSQZDk.png)

Currently, Lightning Watch Bot charges the following fees:

1 hour for 5 sats 
1 day for 90 sats
1 week for 600 sats
1 month for 2400 sats
6 months for 14400 sats
1 year for 27600 sats

### Add a Backup Power Supply

A UPS (uninterruptible power supply) ensures that your node continue to function through minor power fluctuations and power outages.

If you don't shut your Raspberry Pi down properly this is essentually the same as pulling the power cord out of your desktop computer every time you want to shut it down. When this happens, you risk corrupting your device's SD card, as well as data on your hard drive.

The solution is to you plug your device into a high-output power bank. This is basically a juiced-up version of what you might use to charge your phone while camping. The battery pack gets plugged into the wall and your device gets plugged into the battery pack. 

There are several types of devices that offer this feature, and many of them have multiple power outlets onboard, so you can connect other essental items including your router and modem, which will help to eliminate your node's downtime, or at least provide you with enough time to safely power it down until your power is restored. They often have a loud audible alert that will be triggered when the power goes out.
