CompuShare -- Proposal
==============

A program to be used by GPU bitcoin miners "workers" that will either hash or run "pay-per-iteration" Monte Carlo simulations depending on which pays higher at the time. 

Would result in a worldwide distributed supercomputer that could be capable of running 30 000 000 iterations in 1 minute for the cost of $1.


For Clients
==============
There are many [applications of Monte Carlo simulations](http://en.wikipedia.org/wiki/Monte_Carlo_method#Applications). Often there are time sensitive applications. Due to the [embarrassingly parallel](http://en.wikipedia.org/wiki/Embarrassingly_parallel) nature of Monte Carlo iterations the time taken for the code to run is directly proportional to the number of cores available. If enough GPU miners run this code life saving operations could be tested computationally in minutes instead of days.

This is already available to clients via Amazon's Spot Instances. An example of an implementation is described [here](http://christopherpoole.github.io/static/pdfs/Poole%20et%20al.%20-%20Radiotherapy%20Monte%20Carlo%20simulation%20using%20cloud%20computing%20technology.pdf). The downside of using Amazon's service is that the price per instance is rounded up to the hour. A "pay-per-iteration" model would significantly benefit the client over current availability.


For Workers
==============
Firstly, more Bitcoins for the computational buck. But most importantly the running code is all contained within CompuShare, the only files being downloaded are a geometry file, a bunch of random number generator seeds and the initial trajectory of the particles. Your computer would take those initial trajectories and propagate them through the geometry with the random number seeds given.

A difficulty for the miners is that they may need to install more RAM into their mining rig.


Some numbers for the interested
==============
Assume 1000 computers online submitting computation requests to each of the management nodes. Assume each computer has GPU with 500 processing units. Assume each processing unit takes 1 second to process an iteration. This means this cluster would be capable of 30 000 000 iterations every minute.

Assume computer runs at 400W, assume price of electricity is 15c / kWh means 1 minute of computation would cost each computer 0.1c. This means the researcher would only need to pay a little over $1 per minute to access all 1000 nodes. 

Assuming network overhead means there is a 4 minute delay in data transfer this means for $1 this researcher has made a computation take 5 minutes that would have taken days on six CPU cores of the local super computer. 

If an extra cancer patient is able to be treated because of this time saved, the value of that $1 is immense.

Why Bitcoin?
=============
At the moment it really needs to use Bitcoin as there is a Catch 22 limiting its take off. Researchers won't pay for this unless it is significantly better than Amazon. It won't be significantly better than Amazon until there are a large number of nodes on the network. Nodes will only come to the network if it is profitable.
If this program has within it Bitcoin hashing, then GPU miners can mine Bitcoin until the paying clients catch on to the service. Once paying clients begin to use it, it will snow ball. As more clients use the network the payout to the workers will increase. As payout to workers increases, the number of workers will increase.
This needs Bitcoin to start. And because it will be firmly established using Bitcoin it will continue using Bitcoin.

What if I don't want to use Bitcoin?
============
The underlying code will be based on using Bitcoin for the exchange of funds. Once a proof of concept is completed we will approach exchanges to have them implement automatic transfers between Bitcoin and your local currency as necessary.

Difficulties
============
From a researchers point of view it would be highly beneficial if this system ran with [GEANT4](http://en.wikipedia.org/wiki/Geant4). But unfortunately there is not any efficient GEANT4 code adapted for GPUs as of yet.



Making it happen -- Brainstorming results
==============
CompuShare would contain within it all the executable code in an open source fashion. Only geometry files and initial particle trajectories would be downloaded onto workers computers.

This network would contain three categories of nodes, "general", "reliable" and "management". A general node can become a reliable node by completing 100 000 000 consecutive iterations without error. If a reliable node makes an error it is demoted once again to a general node. Should the network begin to bottleneck the reliable nodes that have had the most consecutive iterations are given the opportunity to become management nodes. Management nodes become demoted to reliable nodes if they are completing three standard deviations less transactions than the mean of the management nodes for a sustained amount of time. Management nodes get a "star" rating from both the workers and the clients which is declared to all management nodes and is made public. It is also made public if a management nodes ledger is not up to date for a sustained amount of time.

The network would be run by the management nodes. These nodes will:
* receive, sort and match computation requests
* receive submitted geometry files
* iterate each new geometry file in order to obtain its computational cost (save this iteration and use it to test nodes)
* distribute random number seeds -- have 1% of these be duplicates that are being run on a reliable node -- each set of data paid for must have at least one duplicate seed -- all nodes (including reliable nodes) must have 1% their computations tested in this way by a reliable node.
* record the average (time taken to return a result)/(computational cost) for each node being managed
* receive and hold onto exit particles until worker is paid
* contain the ledger of all the node labels and management node ratings -- the majority ledger is declared true
* management nodes would compete against other management nodes for management fees paid -- there is an upfront management fee to cover the computational cost of running the management node -- and a 1% fee eventually paid to the workers for running "duplicate tests"
* should a management node no longer fulfil its role the workers and clients will give it a bad rating -- this will result in less clients and workers using this management node -- which will result in it eventually being demoted and replaced.

Have CompuShare contain within it the Bitcoin hashing code so that idle GPUs will return to hashing.

Clients would submit their geometry and initial particle trajectories to a management node of their choosing paying a small upfront management fee declared by the management node, at this point the client could choose "cheapest" or "fastest". The management node would then calculate the computational cost of this geometry and declare its "price-per-computational cost" to all the listening nodes. Listening nodes would make their request to run the code and declare how many cores are available in their GPU, they would also have the option to be paid less should they wish. The management node will then assign a given number of iterations to each node. These would be weighted towards being an integer multiple of the number of cores at each node. The method of assigning would either be cheapest then fastest or fastest then cheapest depending on the clients choice. Once the exit trajectories are computed they are encrypted and returned to the management node. At this point the management node declares to the client the payment address and amount due to the worker. The client pays the worker. The worker declares to the management node that they have been paid. The management node sends the decrypted then re-encrypted results to the client.
