# Running BitDust seed node

Here is a step-by-step guide about how to start a full BitDust node that supports other nodes in the network and act as a "seed" node.

You need to own a domain name which is already pointing DNS to your server.

For example, you just started with a new Ubuntu server and logged in as `root` user, first create another user account to be able to run BitDust as a normal user without root priviledges:

        adduser bitdust
        usermod -aG sudo bitdust
        logout


Now log in to your server as `bitdust` user (not as `root`) and do not forget to setup proper SSH access with your Public/Private key. Remember, BitDust software do not require root permissions to run, and no one else can provide you with more privacy than you can arrange by yourself:

        ssh bitdust@my-domain-name.com


Read more about [BitDust installation](install.md) or just follow those few steps bellow.

First clone BitDust sources locally:

        git clone https://github.com/bitdust-io/public.git bitdust


Create BitDust virtual Python environent:
        
        cd bitdust
        python bitdust.py install


Few services needs to be enabled, by default they are turned off because normal user will most probably act as a customer/consumer at the beginning.

Switch ON identity server on your node so you will help other people to identify in the netowork - other users will store their identities on your host:

        bitdust set services/identity-server/enabled true
        bitdust set services/identity-server/host my-domain-name.com
        bitdust set services/identity-server/web-port 8084


This will need a bit more configuration in order to redirect external requests to the server on port 80 to BitDust software listening on port 8084: read more about [Identity server configuration](identity_server.md) to know how to arrange it in a few steps. 

Set UDP port number for you DHT seed:

        bitdust set services/entangled-dht/udp-port 14441


Disable proxy transport and customer service because you do not need those if starting a provider node:

        bitdust set services/proxy-transport/enabled false
        bitdust set services/customer/enabled false


We advice every "seed" node to have a certain identifier format which is based on DNS name of the seed: `root@my-domain-name.com`. In order to do that you need to set domain name of your seed node in the settings, before you create a new identity:

        bitdust set services/identity-propagate/known-servers my-domain-name.com:80:6661


Start BitDust in background:

        bitdust daemon


Now you can interact with BitDust software running on your local machine via HTTP Rest API. Lets create a new identity for your seed node:

        curl -X POST -d '{"username": "root"}' localhost:8180/identity/create/v1


Make sure you also did a backup of your private key and copied that in a safe place.

        curl -X POST -d '{"destination_path": "~/bitdust_identity_backup.txt"}' localhost:8180/identity/backup/v1


Restart BitDust and enjoy, your identity should be accessable on `http://my-domain-name.com/root.xml` if all steps were correct.

        bitdust restart


If you plan to maintain your new BitDust node for awhile and support the network it make sense to include your node into a list of "well known" nodes, which are hard-coded in [networks.json](https://github.com/bitdust-io/public/blob/master/networks.json) file.

You can Fork [Public Git Repository](https://github.com/bitdust-io/public), modify `networks.json` file in your forked repository and start a [Pull Request](https://github.com/bitdust-io/public/pulls) with your changes - this way we can collaborate all together and maintain a list of the most reliable BitDust seed nodes.



<div class=fbcomments markdown="1">
</div>
