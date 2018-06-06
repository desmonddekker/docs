# BitDust Economy

(In progress)


## Intro

A real currency is always like a fluid - same coin can be exchanged for different price in different locations and different situations. Because of this issue every customer must be able to use best currencies suitable for him. But in all cases it must be according to the current market exchange rate - no matter of which currency he was going to use. It is possible to use real currencies like US dollars or Euros, but we believe that best use-case at the moment is to implement blockchain technology to build BitDust economy in the first generation of the network.

We love and encourage a free market, but BitDust project is not focusing on building a new crypto-currency. You will find more detailed info bellow, but saying shortly: the goal is not to accumulate "money" in the network (like Bitcoins/Ethereum does), but implement accouning on consuming/producing of PC resources and make possible to trade it. When you earn some GBH (Gigabytes * hour) you will have to spend them quickly (within same calendar "period") or withdraw into cash or another currency. This way we make sure there will be no speculation or market rush by suppliers.


## Link GBH to real currencies

As soon as supplier and customer stopped their relations (one of them dicided to not extend the contract) contract was finished it is possible to calculate the total value in GBH and define a price in some currency. Supplier is the person who defines the GBH price at the begining. At first he donate some space to the network and do some usefull work for others and gained some GBH in the dstributed contract chain DB.

After that supplier can publish a short info about his offer: he wants to sell some amount of GBH. By adding a new record in the end of contract chain which includes a price and currency type he declares the offer to everyone. The software will do it in a smart way so interested customers always able to "subscribe" for such events and receive those "offers" in real-time, howerver most users will not be "spammed" at all.

Another customer found a good "offer" to buy a GBH from a supplier in distributed contract chain database. He can now send a real money directly to the supplier - in any possible way which is suitable for both of them. Probably supplier wont be albe to accept all of the currencies and all of the payment methods but only few of them. So in the last record of the contract chain supplier puts an info about his preferred payment methods and GBH price he offers.

Customer adds another record to the contract chain now, to place a "bid" - this way he declares that he wants to buy given amount of GBH from that supplier. Now customer is obligated to pay for the contract and he must send the money to supplier. If he do not do that, this contract chain will not be closed and customer "trust" level will be penalized - everyone will be able to verify non-paid contract. Next time when customer would try to find a new supplier he got a bigger chance to be refused. More about user reputation and trust level you can find on that page ...

After sending the payment, customer must "publish" another record to the contract chain to prove the fact that payment was actually made. This is very simillar to real world when you provide a receipt from the payment to someone who wants to verify it.

Now the ball is on supplier's side. After receiving the money supplier will have to confirm the contract and "publish" a final coin in the "chain" and so mark given contract-chain as "paid". If supplier do not do that his own "trust" level will be penalized - other customers always can check that in the distributed contract-chains and decide to not use his service.


## Exchange GBH to real currency



The software will count resources constantly, but periodically it will do a "reset all counters" procedure. Older contracts will be erased automatically from the contracts-chain database - so at any moment only your last finished contracts will have a "value" for other nodes. It is because other nodes have no profits of storing a huge amount of contracts on own PC.

As soon as contract was finished and rewarded it must be cleaned from the database. If contract was not paid within certain period it will be also cleaned. If contract was finished but was not rewarded (paid) it will be still available for longer period (so other people will see it) and finally also will be cleaned. This is not comfort situation for customer because his reputation will go down, it will be explained bellow.





## Payment of completed contracts

Every customer consume storage from network and so he have to pay at some point. From other side suppliers, who donate a lot of PC resources would like to benefit from that.

Because all operations are reported in publicly accessible contract-chains every user able to calculate total amount of consumed/donated resources by any other user. In other words customer know how much PC resources supplier donated and supplirt know how much resources was consumed by customer.

On this basis, any client can pay any supplier contract. It is not necessary to pay directly to the supplier, who provides you with services. You can transfer money to any supplier, with a preliminary analysis of how much the resources granted to other customers by him. The fact of payment will be recorded in the supplier contracts and thus all the other users on the network will know about it.

The payment process starts from the supplier who wants to get paid for his contracts.



Let's describe the whole process of funds moving from customer to supplier step by step:

1. by request from customer A given cashier B calculates total value of all finished contracts by customer A needs to be paid
2. customer A send money in local currency to cashier B - previously they decide about the price for PC resources






## Cashiers

To inpit/output real money into/from the network we introduce another role: "cashier". Se every user can act as a trade agent (or cashier) and help other users to change real money (in local currency) for PC resources and vice versa.

Any cashier must be able to take obligations for all finished contracts belongs to any particular supplier and pays him in local currency by his request. From other side cashier also should be able to support any single customer and receive money from him in order to get paid for all resources was consumed by this customer.



... later customer will have to pay to one of "cashiers" according to amount of mined coins belongs to him (for all his suppliers). From other side, supplier can go to one of "cashiers" and request for refund - accountant will check how much crypto coins belongs to this supplier and calculate total amount in US $, euro, rubles, etc…

... to be continue



## End-to-End example

Alice and Bob provides storage
Carl is a new user in the BitDust network, he found Alice and Bob and requested some amount of GBH
Alice and Bob became suppliers of Carl and he is a customer
They checked in the global contract-chain (no records exist for Carl yet) and decided to sponsor him for free
After some time Alice decided to not extend the contract with Carl
Alice-Carl contract is finalized in contract-chain - Carl confirmed and published the last record with own signature
Carl found another node in the network: Dave. Now Dave is a new supplier of Carl and data was rebuilt on Dave PC
Alice decided to gain real money out of that finished contract with Carl.
Alice is running Ethereum client on her PC (can be light wallet) and able to send/receive blockchain transactions
She generates a new Ethereum address and adds a new record to the finished Alice-Carl contract-chain to declare it
Alice send a transaction (0 ETH) to BitDust smart-contract on Ethereum blockchin with hash of the contract-chain
Now contract-chain Alice-Carl is connected to Ethereum blockchain : everyone could verify it
Ethan is an existing user in BitDust network, he wants to buy PC resources
Ethan founds Alice-Carl contract-chain and Alice transaction in Ethereum blockchain
Ethan send a transaction (X ETH) to BitDust smart-contract on Ethereum blockchin with hash of the Alice-Carl contract-chain
Smart-contract sends (X ETH) to Alice





For example let's take euros as current local currency, and will try to set a price for the storage. 
Consider a customer Alice who agreed to pay 15 euros for 100 GB storage space per one month, so she is fine to spend no more than:

     15 Euros / (100 Gb * 30 days * 24 hours) = 1 Euro for 4800 GBH

She found a supplier Bob who already gained some GBH by providing resources to another customer and willing to sell it for 12 Euros per 100 GB storage per month:

     12 Euros / (100 Gb * 30 days * 24 hours) = 1 Euro for 6000 GBH

But worth to say that nothing about real currencies needs to be defined in the contracts-chain - we only need the actual contract info and the value in GBH. BitDust project is not involved in money transfer at all and have no financial obligations.