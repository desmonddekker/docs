# Distributed Hash-table

(in progress)


## Description

[Distributed hash-table]( https://en.wikipedia.org/wiki/Distributed_hash_table),
or `DHT`, provides an interface close to associative array or dictionary with key/value pair where storage of all pairs (key, value) is distributed into multiple nodes.

Because of such useful DHT’s characteristics as decentralization, scalability and fault-tolerance it is possible to creates an integrated space for service information storage. This means switching to absolutely different approach to organization of network infrastructure rather than common centralized client-server solutions.

Each computer running a BitDust program can be a node in DHT network and stores key/value pairs created by other users.

BitDust software runs DHT network based on implementation from [Entangled](http://entangled.sourceforge.net/) library – its source code is wholly included in the source code of BitDust and is distributed together.



## Data types

Each user node uses different types of service data to interact with other computers in the network. Integrated space lets other users request any key/value pairs, which were previously written by the user in the DHT network, and get actual service information.

The following table has a list of command boxes, which can be written to the hash-table by each node:

* `[IDURL]` 
    user identity file source

* `[username]@[id-server]:address`
    external net address in [IP]:[PORT] format for receiving incoming connections

* `[username]@[id-server]:incoming`
    list of nodes trying to connect to the user at the moment

* `customer_supplier:[index]:[prefix]:[version]`
    list of relations for given customer with other suppliers 
        

## Support BitDust network

If you agree to support other BitDust users when they are connecting to the network and would like to become a "Seed node" in BitDust network you can add your node to the [networks.json](https://github.com/bitdust-io/public/blob/master/networks.json) file which is located in the root of BitDust repository.

Make sure BitDust is running constantly on you machine and it works reliable and connected to the Internet.
You will be a part of BitDust "proto-network" and receive incoming DHT requests from other nodes when they are connecting to the network first time.

This is how Distributed Hash Table works - it is well-scalable, but requires some of the nodes to be on-line all the time. But it shouldn't create a lot of traffic on those nodes because any other node will hit "seed node" only once - when they are joining DHT network for the first time.

To include yourself into a list of "well-known" seed nodes - first create a fork of [Public Git Repository](https://github.com/bitdust-io/public), modify `networks.json` file in your forked repository and start a [Pull Request](https://github.com/bitdust-io/public/pulls) with your changes - this way we can collaborate all together and maintain a list of the most reliable BitDust seed nodes.

Contact with BitDust contributors to notify about this new DHT node was started by you and one of the developers will approve your Pull Request.


<div class=fbcomments markdown="1">
</div>
