# BitDust Roles and Coins

#### Draft 2



## Roles


### Customer

+ Consume resources from other nodes: storage, network traffic, CPU time

+ Pay to Miner with BTC or ETH to "buy a service"

+ Receive "empty" BitDust coin from Miner

+ Send BitDust coin to Supplier to "pay for service"



### Supplier

+ Donate part of own HDD/SSD drive to Customer so that he can store something

+ Receive "signed" BitDust coin from Customer

+ Send "confirmed" BitDust coin to Miner to "sell storage service"

+ Receive BTC or ETH from Miner



### Router (Proxy Server)

+ Help other nodes to connect each other and send/receive packets: re-route network traffic

+ Help other nodes to "hide" real IP address

+ Receive "signed" BitDust coin from Customer

+ Send "confirmed" BitDust coin to Miner to "sell network bandwidth service"

+ Receive BTC or ETH from Miner



### Rebuilder

+ Help new Supplier to reconstruct "missed" data fragments an store Customer data

+ Receive "signed" BitDust coin from Supplier

+ Send "confirmed" BitDust coin to Miner to "sell CPU service"

+ Receive BTC or ETH from Miner



### Miner

+ Help other nodes to get read-access to blockchain

+ Publish transactions on blockchain for other nodes

+ Receive BTC or ETH from Customer

+ Generate "empty" BitDust coin and give it to Customer

+ Receive "confirmed" BitDust coin from Supplier, Rebuilder or Router

+ Send BTC or ETH to Supplier, Rebuilder or Router

+ Finally he "burn" BitDust coin to "proof storage"



## Rules

1. Every Customer can make only one transaction per Miner. If he requires more coins - he will have to find another Miner in the network

2. Every Supplier, Rebuilder or Router can make only one transaction per Miner. If you want to sell more "confirmed" coins to "burn" them - you will have to find another Miner in the network

3. BitDust coin can not be transferred after it was "burn"

4. A fixed maximum life-cycle duration for each BitDust coin will be decided later (3-12 months) - the whole BitDust blockchain will be periodically cleaned up and mining will start from scratch all over again in next cycle
