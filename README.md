## Recover Funds on the Lightning Network for your Family.

### Don't take your private keys to your grave.

[![Watch the video](https://img.youtube.com/vi/Pz4io1CQh34/0.jpg)](https://youtu.be/Pz4io1CQh34)



<br>
The goal of this document is to help your family recover offchain funds or funds in your lightning channels in case a tragic event occurs to the node operator such as death.

<br>
This document covers LND Nodes only and does not aim to cover step by step instructions for recovering funds since nodes differ based on the distributions one uses but instead help the node operator use this as a base version to write further instructions for their family.
<br>

### What's needed for recovery?
1. 24 word seed phrase
2. Wallet password (for Umbrel users, this is probably your SSH Password)
3. SSH Access (Host@domainname/IPaddress and SSH Access Password or hardware keys)

<br>
<br>
Need help? Plebs are always willing to help, download the telegram app and join the telegram group `PLEBNET` and ask for help.
https://t.me/plebnet or visit https://plebnet.wiki

<br>

DO NOT EVER GIVE ANYONE the seed phrase, wallet password or SSH Password. YOUR FUNDS WILL BE STOLEN IF YOU DO.

<br>

### Accessing the wallet:
The easiest way one can access their onchain wallet is by importing the 24 word seed phrase into bluewallet. Download BlueWallet on your smart phone, hit the plus icon and select import wallet and enter the 24 words with spaces in between to perform the import.
Importing seed into bluewallet gives access to onchain funds in your LND wallet and can be spent or moved to another wallet.
<br>

https://user-images.githubusercontent.com/84944042/145740249-13a81784-89ca-4587-819d-c0c8ea20ec7f.mov

<br>

### Recovering offchain funds
1. SSH into the node: Give them the host and domain name/IP address that you use to ssh into your node. For example umbrel users use `umbrel@umbrel.local`
Then enter the password/hardware key to access the node.
<br>

https://user-images.githubusercontent.com/84944042/145739503-e7865cc7-16d8-422e-9105-89d5cf39ca5a.MP4

<br>
<br>
2. Close All Channels: Type this command `lncli closeallchannels` and hit enter. (On umbrel nodes it is, `~/bin/lncli closeallchannels`. This command cooperatively closes channels that are online and force closes all offline channels. It should give a closing trasaction ID for each every channel.
<br>

https://user-images.githubusercontent.com/84944042/145739481-5959bb28-3250-45dd-b05d-65820bbabbe6.MP4

<br>
3. Copy the transaction ID and search in mempool.space and wait for one confirmation, upon a confirmation, refresh the imported wallet in Bluewallet and the funds should appear. A confirmation implies the block your transaction is inside moves from left side to the right side (from green to blue color).
<br>

https://user-images.githubusercontent.com/84944042/145740585-2f8f1b8e-8856-42db-8ad0-99e3fc3fb04d.mov

<br>
<br>
4. After all transactions have at least one confirmation, all funds should appear in bluewallet. Note that, if any of the closures are force closures, there will be a timelock for you to spend those funds. DO NOT POWER OFF THE NODE UNTIL ALL CHANNELS ARE FULLY CLOSED. Ideally wait upto 3 weeks before powering off the node to make sure all funds have returned.





