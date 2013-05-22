CompuShare -- Proposal
==============

A program to be used by GPU bitcoin miners "workers" that will either hash or run "pay-per-iteration" Monte Carlo simulations depending on which pays higher at the time. 


Benefit to Clients
==============
There are many [applications of Monte Carlo simulations](http://en.wikipedia.org/wiki/Monte_Carlo_method#Applications). Often there are time sensitive applications. Due to the [embarrisingly parallel](http://en.wikipedia.org/wiki/Embarrassingly_parallel) nature of Monte Carlo iterations the time taken for the code to run is directly proportional to the number of cores available. If enough GPU miners run this code life saving operations could be tested computationally in minutes instead of days.

This is already available to clients via Amazon's Spot Instances. An example of an implementation is described [here](http://christopherpoole.github.io/static/pdfs/Poole%20et%20al.%20-%20Radiotherapy%20Monte%20Carlo%20simulation%20using%20cloud%20computing%20technology.pdf). The downside of using Amazon's service is that the price per instance is rounded up to the hour. A "pay-per-iteration" model would significantly benefit the client over current availability.


Benefit to Workers
==============
GPU miners would be given the choice to hash or to run more profitable computations. Furthermore as a side effect this could result in a slight redection of the bitcoin difficulty.



Current idea to get this to work
=============
Use GPUs for the MC simulations. Have the code that is being sent open source. Since the code is being run on a GPU each set of data could represent about a thousand particles. Have a trusted node purely computing random numbers. This trusted node would test the trustworthiness of each node by sending one of these 1000 particles to be based on the same random numbers sent to a secondary trusted node. This would mean for every 1000 nodes you would need 1 extra trusted node. (and maybe quite a few more random number generator trusted nodes.)

Remove the idea of sandbox. Remove the idea of trying to make the calculated code closed source.

Eventually have it set up so that the user running the program on their GPU can automatically start hashing again if no computation is available that is worth it.
