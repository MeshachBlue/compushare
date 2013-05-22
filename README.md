CompuShare -- Proposal
==============

A program to be used by GPU bitcoin miners "workers" that will either hash or run "pay-per-iteration" Monte Carlo simulations depending on which pays higher at the time. 


For Clients
==============
There are many [applications of Monte Carlo simulations](http://en.wikipedia.org/wiki/Monte_Carlo_method#Applications). Often there are time sensitive applications. Due to the [embarrisingly parallel](http://en.wikipedia.org/wiki/Embarrassingly_parallel) nature of Monte Carlo iterations the time taken for the code to run is directly proportional to the number of cores available. If enough GPU miners run this code life saving operations could be tested computationally in minutes instead of days.

This is already available to clients via Amazon's Spot Instances. An example of an implementation is described [here](http://christopherpoole.github.io/static/pdfs/Poole%20et%20al.%20-%20Radiotherapy%20Monte%20Carlo%20simulation%20using%20cloud%20computing%20technology.pdf). The downside of using Amazon's service is that the price per instance is rounded up to the hour. A "pay-per-iteration" model would significantly benefit the client over current availability.


For Workers
==============
Firstly, more Bitcoins for the computational buck. But most importantly the running code is all contained within CompuShare, the only files being downloaded are a geometry file, a bunch of random number generator seeds and the initial trajectory of the particles. Your computer would take those initial trajectories and propagate them through the geometry with the random number seeds given.

A difficulty for the miners is that they may need to install more RAM into their mining rig.


Making it happen -- Brainstorming results
==============
Begin with [Monte Carlo eXtreme](http://mcx.sourceforge.net/cgi-bin/index.cgi) for the running of Monte Carlo simulations on graphics cards.

CompuShare would contain within it all the executable code in an open source fashion. Only geometry files and initial particle trajectories would be downloaded onto workers computers.

This network would contain three categories of nodes, "untrusted", "trusted" and "trusted management"/"management". An untrusted node can become trusted by completing 100 000 000 consecutive iterations without error. If a trusted node makes an error it is demoted to an untrusted node. Trusted nodes are randomly given the opportunity to become managment nodes if the network is bottlenecking. Management nodes become demoted to trusted nodes if they are completing two standard deviations less transactions than the mean of the management nodes for a sustained amount of time.

The network would be run by the trusted management nodes. These nodes will:
* receive, sort and match computation requests
* receive submitted geometry files
* distribute random number seeds -- have 1% of these be duplicates between untrusted nodes to test for cheating -- each untrusted node must have at least one unknown duplicate seed -- have at least 5% of duplicates be tested by a trusted node
* receive and hold onto exit particles until worker is paid
* contain the ledger of all the node labels -- the majority ledger is declared true
* trusted management node would compete against other trusted management nodes for management fees paid

Have CompuShare contain within it the Bitcoin hashing code so that idle GPUs will return to hashing.

