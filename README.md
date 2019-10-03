# information
information



# geth 실행
## JSON RPC API 

geth --networkid 15 --nodiscover --maxpeers 0 --datadir sotolab --rpc --rpcaddr "0.0.0.0" --rpcport 8545 --rpccorsdomain "*" --rpcapi "admin,db,eth,debug,miner,net,shh,txpool,personal,web3" console 2>> geth.log

geth --rpc --rpcaddr="localhost" --mine --unlock=primary --rpcport="8080" --rpccorsdomain="http://localhost:3000" --loglevel=5 --maxpeers=0

geth --rpc --rpccorsdomain "http://localhost:3000"


./geth --networkid 15 --nodiscover --maxpeers 0 --datadir p1 --rpc --rpcaddr "0.0.0.0" --rpcport 8545 --rpccorsdomain "*" --rpcapi "admin,db,eth,debug,miner,net,shh,txpool,personal,web3" console 2>> geth.log

./geth --datadir sotolab --rpc --rpcaddr "0.0.0.0" --rpcport 8545 --rpccorsdomain "*" --rpcapi "admin,db,eth,debug,miner,net,shh,txpool,personal,web3" --port 3030 --nodiscover --networkid 1001 console
geth --identity "PrivateNetwork" --datadir "sotolab" --port "30303" --rpccorsdomain "*" --nodiscover --networkid 1900 --nat "extip:0.0.0.0" --rpc --rpcaddr "0.0.0.0" --rpccorsdomain "*" --rpcport "8545" --nodiscover --rpcapi "admin,db,eth,debug,miner,net,shh,txpool,personal,web3" console


# geth console
> personal.newAccount("eth")

> eth.accounts[0]

> eth.blockNumber

> eth.hashrate

> eth.coinbase

> miner.setEtherbase(eth.accounts[1])

> eth.getBalance(eth.accounts[0])

> eth.sendTransaction({from: eth.accounts[1], to: eth.accounts[0], value: web3.toWei(10, "ether")})

> personal.unlockAccount(eth.accounts[0], "eth")

> eth.pendingTransactions

> eth.getBalance(eth.accounts[1])

> miner.start()

> miner.stop()

> web3.fromWei(eth.getBalance(eth.accounts[0]), "ether") 

> eth.getTransaction("0x681001dab2665fb128adff42c83470bc9eae9249e4d963dbc0071a4e22fa8fd7")

> eth.getBlock(1230)

## 멀티 노드 구성
"enode://442bdb0a9a0aad7d6e3f48346c1f0afa32925b5001c0b36a959881a122a6023c59bc0c6c5a29301a0a940645f43b09b273ff92812cd83b0d2f7ba6ba6ff10e51@0.0.0.0:30303"

$ geth --datadir "p1" --port 30301 --networkid 15 --ipcdisable console 

$ geth --datadir "p2" --port 30302 --networkid 15 --ipcdisable console 

$ geth --datadir "p3" --port 30303 --networkid 15 --ipcdisable console 



> admin.nodeInfo.enode
"enode://8f288e577053333c49a6ae4728e117be06e6dc39243400af69439bcfbffc2500fd3c08568772c0c01accadb193fe9c3f29336dc2a08c19c9a1e4d111b017edab@0.0.0.0:30301"

> net.peerCount
2

> admin.peers


> admin.addPeer("enode://8f288e577053333c49a6ae4728e117be06e6dc39243400af69439bcfbffc2500fd3c08568772c0c01accadb193fe9c3f29336dc2a08c19c9a1e4d111b017edab@0.0.0.0:30301")
> net.peerCount
> admin.peers
> personal.newAccount(“eth”)

> eth.sendTransaction({from: eth.coinbase, to: "0x032875e095dc9319c2750db2a324209c765dee71", value: web3.toWei(1, "ether")})


#솔루션
크롬 브라우저의?Access-Control-Allow-Origin?문제가 발생한다면, https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi?hl=ko

npm install --save web3@^0.20.0

1. uninstall / reinstall node (deleted all related folders in local directories too, including in Roaming)
2. in POWERSHELL as Administrator: npm install --global --production windows-build-tools
3. npm install --save --no-optional web3




---------------------------------
playground
https://blocko-1.gitbook.io/coinstack-api-reference/

https://sunstar.run.goorm.io/
