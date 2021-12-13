## Recover Funds on the Lightning Network for your family.
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

### Accessing the wallet:
The easiest way one can access their onchain wallet is by importing the 24 word seed phrase into bluewallet. Download BlueWallet on your smart phone, hit the plus icon and select import wallet and enter the 24 words with spaces in between to perform the import.
Importing seed into bluewallet gives access to onchain funds in your LND wallet and can be spent or moved to another wallet.
<br>
![Import Seed Into BlueWallet](./resources/bluewalletImport.MP4)

<br>

### Recovering offchain funds
1. SSH into the node: Give them the host and domain name/IP address that you use to ssh into your node. For example umbrel users use `umbrel@umbrel.local`
Then enter the password/hardware key to access the node.
<br>
https://user-images.githubusercontent.com/84944042/145739242-6aa5446f-6edb-4080-b0e4-47908f23af67.mov
<br>
2. Close All Channels: Type this command `lncli closeallchannels` and hit enter. (On umbrel nodes it is, `~/bin/lncli closeallchannels`. This command cooperatively closes channels that are online and force closes all offline channels. It should give a closing trasaction ID for each every channel.
<br>
https://user-images.githubusercontent.com/84944042/145739219-a4541219-957c-403f-90c1-f8fb252eb078.mov

<br>
3. Copy the transaction ID and search in mempool.space and wait for one confirmation, upon a confirmation, refresh the imported wallet in Bluewallet and the funds should appear. A confirmation implies the block your transaction is inside moves from left side to the right side (from blue to green color).
<br>
![Search Mempool](./resources/mempool.MP4)
<br>
4. After all transactions have at least one confirmation, all funds should appear in bluewallet. Note that, if any of the closures are force closures, there will be a timelock for you to spend those funds. DO NOT POWER OFF THE NODE UNTIL ALL CHANNELS ARE FULLY CLOSED. Ideally wait upto 3 weeks before powering off the node to make sure all funds have returned.
<br>
<br>
Need help? Plebs are always willing to help, download the telegram app and join the telegram group `PLEBNET` and ask for help.
https://t.me/plebnet or visit https://plebnet.wiki

<br>

DO NOT EVER GIVE ANYONE the seed phrase, wallet password or SSH Password. YOUR FUNDS WILL BE STOLEN IF YOU DO.
