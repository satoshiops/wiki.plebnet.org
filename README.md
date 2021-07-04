# PLEBNET for plebs

## Getting Started

You need a [Lightning Network](https://en.wikipedia.org/wiki/Lightning_Network) node and [Telegram](https://telegram.org/) in order join [PLEBNET](http://plebnet.org).
- Read the [bitcoiner.guide/lightning](https://bitcoiner.guide/lightning/) guide to get an overview of how the lighting network works.

### Node

There's several newbie options for getting a Lightning node set up and running
* [RaspbiBlitz](https://github.com/rootzoll/raspiblitz) is a great option that runs on Raspberry Pi v4+
* [Umbrel](https://getumbrel.com/) is a newbie-friendly package that runs on Raspberry Pi v4+
  * [BTC SESSIONS](https://youtu.be/fppmhqjqh2E) has a good video walkthrough for getting started with Raspberry Pi and Umbrel
  * **Security note for Umbrel:** *Your Umbrel node is only as secure as your network (WiFi/LAN).* Be sure to read the [Security Disclosure](https://github.com/getumbrel/umbrel/blob/master/SECURITY.md) from the Umbrel team.
* [Start9](https://start9.com/) is an all-in-one option that includes the necessary hardware
* [myNode](https://www.mynodebtc.com/) is another all-in-one with hardware
* [RaspiBolt](https://stadicus.github.io/RaspiBolt/) has some good information on how to set up the necessary services manually

### Telegram

PLEBNET discussion and coordination happens on the Telegram chat platform.

Download the [Telegram app](https://telegram.org/) and join the [PLEBNET](http://kycjelly.com) group.

The companion Telegram channel [PLEBNET Library](https://t.me/plebnetlibrary) contains high quality materials collected from chat group traffic.

### CheeseRobot ₿

A Telegram bot that will allow you to join and interact with the PLEBNET. 

You'll want to send a message to `@cheeserobot` to claim and add your node. Start with `/claim` and follow the instructions to get add your node id. Then, in the PLEBNET channel, use `/id@cheeserobot` to get yourself added to the graph.

## Opening Channels

### Add Liquidity

Generate a Lightning wallet and add some funds so that you can open channels. Keep in mind that PLEBNET prefers [girthy channels](#keep-it-girthy), so fund your node accordingly.
 

### Find Nodes in PLEBNET Telegram Group

If you're not yet able or willing to offer girthy channels and just want to get started with a smaller amount of sats, [Turgidson](https://amboss.space/node/0381de1709efbda38f9afd2d47399caa19a2630c0c795acd24755efa442685fc7d) is for PLEBNET newbies and will accept channels as low as 20k.

You may want to check out [Lightning Routing: The First 30 Days](https://www.youtube.com/watch?v=qnj-ix45tVw) to get some ideas

Otherwise, you'll need to find some other nodes in PLEBNET to open channels with.

You can go to [http://graph.plebnet.org/](http://graph.plebnet.org/) to see the current visual graph of nodes, or type `/graph@cheeserobot group` in the PLEBNET chat.  `/groupnodes@cheeserobot` will output a list of the 50 most recent members and nodes. You can contact plebs form the graph or list and see if they'd like to open a channel.

You can also just ask in the PLEBNET channel if anyone is interested in opening a channel with you.

### Other Channel Sources

If you're just getting started and want to find some other nodes to open channels with, here's some places where other plebs have had success:

* [Lightning Network Plus](https://lightningnetwork.plus/)
* [Ring of Fire](https://github.com/Rings-of-Fire/ring-of-fire/wiki)
* [Lightning Conductor](https://mainnet.lightningconductor.net/)
* [Umbrel Opening Channel Requests](https://community.getumbrel.com/t/opening-channels-requests/66)
* [moneni.com Node Match](https://www.moneni.com/)

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

The solution for this is to change your router's settings to lock the IP address used by your node. Depending on the type of router you use, this might be referred to as a **manually-assigned IP**, a **reserved IP**, or you may need to simply turn off **automatic IP** assignment. You might have to look in the advanced settings section to find this feature. Once you've set the IP address, you shouldn't have to reboot your node, but if you do, it should retain the same IP address when it comes back up.

![Image](https://i.imgur.com/OwazT9K.jpeg)
Example of the Reserved IP settings screen on the Google Home app.

### Make Friends With Lightning Watch Bot

One simple way to be notified in the event your node becomes unavailable is to register it with @lightningwatchbot, a Telegram bot that will keep an eye on your node's up/down staus. Start a conversation with the bot, and it will walk you through the steps to connect your node. As a free service, it will send you alerts on a one hour delay. For a faster response time, you can open a channel of any size with the bot (a great way to practice opening channels) and send it a small payment to receive notifications for your desired duration. 

![Image](https://i.imgur.com/voSQZDk.png)

Currently, Lightning Watch Bot charges the following fees:

* 1 hour for 5 sats 
* 1 day for 90 sats
* 1 week for 600 sats
* 1 month for 2400 sats
* 6 months for 14400 sats
* 1 year for 27600 sats

### Add a Backup Power Supply

A UPS (uninterruptible power supply) ensures that your node continue to function through minor power fluctuations and power outages.

If you don't shut your Raspberry Pi down properly this is essentually the same as pulling the power cord out of your desktop computer every time you want to shut it down. When this happens, you risk corrupting your device's SD card, as well as data on your hard drive.

The solution is to you plug your device into a high-output power bank. This is basically a juiced-up version of what you might use to charge your phone while camping. The battery pack gets plugged into the wall and your device gets plugged into the battery pack. 

A UPS should only be relied on to provide you with enough time to safely shut down your node until your power is restored. You should not connect your router or modem to the UPS due to potential data corruption that may occur if your node is in the process of writing to the disk when a power outage occurs. 

Many UPS devices have a loud audible alert that will be triggered when the power goes out. 

Here are some options to consider:

* https://amzn.com/B01FWAZEIU
* https://amzn.com/B00DBAA696
* https://amzn.com/B07BXZPF99
* https://amzn.com/B073Q3BSPG

#### Advanced UPS Setup
If you want to automate a graceful shutdown for the node once the UPS power capacity goes to a minimum level, you can connect the UPS Serial port (via USB) to the Raspberry Pi or PC and have it communicate with the UPS
once configuring the UPS daemon in the Pi or you Linux setup correctly, it will initiate a graceful shutdown if the capacity hits 5%

The following steps should be run via SSH:

```
sudo apt-get install apcupsd
sudo nano /etc/default/apcupsd
```
In /etc/default/apcupsd change 'ISCONFIGURED=no' to 'ISCONFIGURED=yes'

```
sudo nano  /etc/apcupsd/apcupsd.conf
```

Change the values as below, make sure the DEVICE field is empty, the default is /dev/ttyS0 and should be cleared.
```
UPSNAME myups
UPSCABLE usb
UPSTYPE usb
DEVICE
```
Note - Make sure the 
Restart apcupsd
```
sudo apcupsd restart
```

Check UPS status:
```
apcaccess status
```
output example:
```
$ apcaccess status
APC      : 001,035,0900
DATE     : 2021-06-14 02:13:51 +0000
HOSTNAME : umbrelmavic
VERSION  : 3.14.14 (31 May 2016) debian
UPSNAME  : myups
CABLE    : USB Cable
DRIVER   : USB UPS Driver
UPSMODE  : Stand Alone
STARTTIME: 2021-06-13 01:38:35 +0000
MODEL    : Back-UPS ES 350
STATUS   : ONLINE
LINEV    : 120.0 Volts
LOADPCT  : 0.0 Percent
BCHARGE  : 100.0 Percent
TIMELEFT : 36.4 Minutes
MBATTCHG : 5 Percent
MINTIMEL : 3 Minutes
MAXTIME  : 0 Seconds
SENSE    : High
LOTRANS  : 88.0 Volts
HITRANS  : 139.0 Volts
ALARMDEL : 30 Seconds
BATTV    : 13.7 Volts
LASTXFER : Unacceptable line voltage changes
NUMXFERS : 1
XONBATT  : 2021-06-13 01:50:34 +0000
TONBATT  : 0 Seconds
CUMONBATT: 251 Seconds
XOFFBATT : 2021-06-13 01:54:45 +0000
STATFLAG : 0x05000008
SERIALNO : XXXXXXXXXXXX
BATTDATE : 2007-06-08
NOMINV   : 120 Volts
NOMBATTV : 12.0 Volts
FIRMWARE : 823.B1.D USB FW:B1
END APC  : 2021-06-14 02:13:55 +0000
```

Once the output looks correct, specifically the STATUS shows as ONLINE, you can test the setup by disconnecting the UPS from the main power, watch the message prompts on the terminal and and let the battery drain until the point that a showdown will be initiated, this will confirm that your setup is correct.   

## Let's Get Personal

### How to Set an Alias and Color for Your Node

Personalizing your node makes it easier for your node to be identified by others. You can give it a name and a color that shows up when your node is viewed using external applications, such as [1ml](https://1ml.com/) and [graph.kycjelly.com](http://graph.kycjelly.com/). 

In order to do this, you will need to access your node via the command line terminal using SSH. If you're using Umbrel/LND, use [these instructions](https://lightningwiki.net/index.php/Setting_alias_and_color_for_Umbrel).

If you're familiar with the Linux command line, you'll find this step very simple. [You can view a cheat sheet of common Linux commands here](https://www.guru99.com/linux-commands-cheat-sheet.html).

![Image](https://i.imgur.com/tElum7G.jpg)

Important note: Whenever you update your node's software, you will need to reset these settings, so you should take note of the these settings for reference. (Do not overwrite the new lnd.conf with your old version, just update those specific lines.)
