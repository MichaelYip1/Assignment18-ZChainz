# Assignment 18 - ZBank ("ZChain")

This repo contains key information on how to operate ZBank testnet blockchain "ZChain". Inspired by 2Chainz

![2chainz](Screenshots/2chainz.jpg)

In order to run execute the blockchain, you will need the GO Ethereum (geth) package downloaded and extracted. The environment being used to run the blockchain is within the folder where geth.exe is located.

ZChain contains 2 nodes, "1chain" and '2chainz' configured as per below graphic.

![config](Screenshots/puppeth_config.png) 

## Blockchain Details

Chain ID: 467 

Testnet: zchain

1chain node <br>
Node password: chainz <br>
Node Address: 0x5e29Ca7380D0e67D632368C5c76a90190e148Cec <br>
Node Keystore Address: 1chain\keystore\UTC--2021-08-14T04-56-47.268003000Z--5e29ca7380d0e67d632368c5c76a90190e148cec<br>
Node enode ID: enode://9dbee322dc225cbf9775343992d718f8d19dff84f124abb918ae4589652cfe37383447ab7b9fc1ee92b6de34cf47068140843c87c8b1f37b3df7cdb2227ac250@127.0.0.1:30303<br>

2chainz<br>
Node password: chainz<br>
Node Address: 0x1b3BF68c50B2837E74691aE74BDde148985baF76<br>
Node Keystore Address: 2chainz\keystore\UTC--2021-08-14T04-57-24.859493600Z--1b3bf68c50b2837e74691ae74bdde148985baf76<br>


## 1. Initiate the blockchain nodes in 2 separate terminals:

To initiate node "1chain", use the following command: 
./geth --datadir 1chain --unlock "0x5e29Ca7380D0e67D632368C5c76a90190e148Cec" --mine --rpc --allow-insecure-unlock

Note:<br>
./geth executes the geth.exe application.<br>
--datadir directs the command to the node selected.<br>
--unlock issues a command to unlock and access the node with the password given<br>
--mine issues the mine command for the node<br>
--rpc allows remote applications to access your nodes<br>
--allow-insecure-unlock makes the unlock process possible otherwise the http access remains forbidden.<br>

A successful mined block will look like the following:
![1chain](Screenshots/1chain.png)

 Also note that we used 1chain's node address in our command.

Now, do the same with the second node '2chainz' using the following command:
./geth --datadir 2chainz --unlock "0x1b3BF68c50B2837E74691aE74BDde148985baF76" --mine --port 30304 --bootnodes "enode://9dbee322dc225cbf9775343992d718f8d19dff84f124abb918ae4589652cfe37383447ab7b9fc1ee92b6de34cf47068140843c87c8b1f37b3df7cdb2227ac250@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

And it should look like this:
![2chainzz](Screenshots/2-chainz.png)

Note:<br>
--port is used to customise the port<br>
--bootnodes is used to connect to a different node with the enode address belong to 1chain<br>
--ipcdisable is used to disable ipc connection as it is not required.<br>

CONGRATZ! You have successfully mined ETH.

## 2. Transact using MyCrypto

Change network. Add a custom node with the following values:<br>
Node Name: zchainz<br>
Network: Custom<br>
Network Name: zchainz<br>
Currency: ETH<br>
Chain ID: 467<br>
URL: http://127.0.0.1:8545<br>

![nodesetup](Screenshots/nodesetup.png)


View & Send. Click Keystore file on the View & Send tab. Select the keystore for 1chain and unlock with password given above. You will then be prompted to a Send Trasanction page.

Input as follows:-<br>
To Address: 2chainz address<br>
Amount: whatever amount you desire<br>
Others remain default<br>

![transact](Screenshots/transact.png)

You will then be checking the TX Status page with the hash given from the transaction. 

![sent](Screenshots/transactions1300888333.png)