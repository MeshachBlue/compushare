CompuShare -- Proposal
==============

A program to be used by GPU bitcoin miners "workers" that will either hash or run "pay-per-iteration" Monte Carlo simulations depending on which pays higher at the time. 

From the researchers point of view, Monte Carlo simulations run many many thousands of iterations of code. Each iteration is independent of each other iteration and can be run in any order. This iterative process is perfect for distributive computing. Unfortunately due to limited hardware an iteration of 16 000 000 particles often takes days. This limits medical applications and research progress.

For applications of Monte Carlo simulations see http://en.wikipedia.org/wiki/Monte_Carlo_method#Applications.

One example of this already implemented using Amazon's Spot Instances is given here:
http://christopherpoole.github.io/static/pdfs/Poole%20et%20al.%20-%20Radiotherapy%20Monte%20Carlo%20simulation%20using%20cloud%20computing%20technology.pdf
In this case though Amazon prices are rounded up to the hour, making a very large number of cores, for a very short amount of time more expensive.

CompuShare, when completed, would give researchers the option to pay bitcoin miners worldwide in an auction "pay-per-iteration" style, with bitcoins, for the ability to run their iterations distributively across the node network. 
Should enough GPU miners run this code researches would have access to inexpensive, exceptionally quick Monte Carlo results.

All money would be transferred as bitcoins to the bitcoin mining network. This injection of value into the bitcoin network would be exceptionally beneficial for the network.


Current idea to get this to work
=============
Use GPUs for the MC simulations. Have the code that is being sent open source. Since the code is being run on a GPU each set of data could represent about a thousand particles. Have a trusted node purely computing random numbers. This trusted node would test the trustworthiness of each node by sending one of these 1000 particles to be based on the same random numbers sent to a secondary trusted node. This would mean for every 1000 nodes you would need 1 extra trusted node. (and maybe quite a few more random number generator trusted nodes.)

Remove the idea of sandbox. Remove the idea of trying to make the calculated code closed source.

Eventually have it set up so that the user running the program on their GPU can automatically start hashing again if no computation is available that is worth it.
