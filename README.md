# BOE-Token


<h2>1.	Installation Private Ethereum Node</h2>

<b>sudo apt-get install software-properties-common<br />
sudo add-apt-repository -y ppa:ethereum/ethereum<br />
sudo apt-get update<br />
sudo apt-get install ethereum<br /></b>

<h2>2. Creating node</h2>

<b>mkdir /home/privateeth<br />
cd /home/privateeth<br />
nano genesis.json<br />

genesis.json<br />
{<br />
    "coinbase" : "0x0000000000000000000000000000000000000000",<br />
    "difficulty" : "0x20000",<br />
    "extraData" : "",<br />
    "gasLimit" : "0x2fefd8",<br />
    "nonce" : "0x0000000000000042",<br />
    "mixhash" : "0x0000000000000000000000000000000000000000000000000000000000000000",<br />
    "parentHash" : "0x0000000000000000000000000000000000000000000000000000000000000000",<br />
    "timestamp" : "0x00",<br />
    "alloc": {},<br />
    "alloc": {},<br />
    "config": {<br />
        "chainId": 9000151,<br />
        "homesteadBlock": 0,<br />
        "eip155Block": 0,<br />
        "eip158Block": 0<br />
    }<br />
}<br />
</b>
Creating the blockchain.<br />
<b>geth --datadir /home/privateeth init genesis.json</b><br />

<h2>3. Starting private node/</h3>

<b>geth --datadir /home/privateeth/ --networkid 45421 --verbosity 3 -ipcdisable --rpc --port 40301 --rpcport 8545 --rpcaddr 127.0.0.1 --rpcapi="db,eth,net,web3,personal,web3" --gasprice 0  console 2>> /home/privateeth/eth.log</b><br /> 



In console add peer<br />
<b>admin.addPeer('enode://5d094dbef9e064c2925f755681c4869b42eefd332325c16f5aaa8757d4d89dd24c84cd8cce6d52e92a1592954fdd7e4202b334eee72a544cbe5798ff4ecc4754@88.99.94.176:40301')</b><br />

Verify that the peer has started<br />
<b>admin.peers</b><br />

Creating new account<br />
<b>personal.newAccount()</b><br />

Creating password for new account<br />
Starting the blockchain <br />
<b>miner.start(1)</b><br />

To connect blockchain, you can use the client Mist with keys <br />
<b>mist --rpc 'http://127.0.0.1:8545'</b><br />
