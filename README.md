# BOE-Token


1.	Installation Private Ethereum Node

sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum

2. Creating node

mkdir /home/privateeth
cd /home/privateeth
nano genesis.json

genesis.json
{
    "coinbase" : "0x0000000000000000000000000000000000000000",
    "difficulty" : "0x20000",
    "extraData" : "",
    "gasLimit" : "0x2fefd8",
    "nonce" : "0x0000000000000042",
    "mixhash" : "0x0000000000000000000000000000000000000000000000000000000000000000",
    "parentHash" : "0x0000000000000000000000000000000000000000000000000000000000000000",
    "timestamp" : "0x00",
    "alloc": {},
    "alloc": {},
    "config": {
        "chainId": 9000151,
        "homesteadBlock": 0,
        "eip155Block": 0,
        "eip158Block": 0
    }
}
Creating the blockchain.
geth --datadir /home/privateeth init genesis.json

3. Starting 

geth --datadir /home/privateeth/ --networkid 45421 --verbosity 3 -ipcdisable --rpc --port 40301 --rpcport 8545 --rpcaddr 127.0.0.1 --rpcapi="db,eth,net,web3,personal,web3" --gasprice 0  console 2>> /home/privateeth/eth.log 



In console add peer
admin.addPeer('enode://5d094dbef9e064c2925f755681c4869b42eefd332325c16f5aaa8757d4d89dd24c84cd8cce6d52e92a1592954fdd7e4202b334eee72a544cbe5798ff4ecc4754@88.99.94.176:40301')

Verify that the peer has started
admin.peers

Creating new account
personal.newAccount()

Creating password for new account
Starting the blockchain 
miner.start(1)

To connect blockchain, you can use the client Mist with keys 
mist --rpc 'http://127.0.0.1:8545'
