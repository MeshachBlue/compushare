CompuShare -- Proposal
==============

An alternative bitcoin "miner".

Pays the miner more bitcoins by giving the miner the option to run a researcher's Monte Carlo iteration.

From the researchers point of view, Monte Carlo simulations run many many thousands of iterations of code. Each iteration is independent of each other iteration and can be run in any order. This iterative process is perfect for distributive computing. Unfortunately due to limited hardware an iteration of 16 000 000 particles often takes days. This limits medical applications and research progress.

For applications of Monte Carlo simulations see http://en.wikipedia.org/wiki/Monte_Carlo_method#Applications.

CompuShare, when completed, would give researchers the option to pay bitcoin miners worldwide in an auction style, with bitcoins, for the ability to run their iterations distributively across the node network. As a result researchers would have access to practically instantaneous Monte Carlo results. Particular radiation treatments could be implemented days earlier, the progress of physics research worldwide would increase, underfunded universities could have access to a distributive super computer for a very reasonable cost.

All money would be transferred as bitcoins to the bitcoin mining network. There would be several beneficial effects to the bitcoin economy as a result:
* This would stabilise the bitcoin economy. 
* It would make it so all computers could once again effectively mine bitcoin (not just ASIC's). 
* It would do leaps and bounds for legitimising the currency. 
* Make it exceptionally more liquid. 
* Allow users to very effectively trade electricity for bitcoins effectively bypassing exchanges. 
* The price would no longer be defined by a few exchanges and their traders, instead it would be decided by the value of computation (which is very valuable).


Current idea to get this to work
=============
Use GPUs for the MC simulations. Have the code that is being sent open source. Since the code is being run on a GPU each set of data could represent about a thousand particles. Have a trusted node purely computing random numbers. This trusted node would test the trustworthiness of each node by sending one of these 1000 particles to be based on the same random numbers sent to a secondary trusted node. This would mean for every 1000 nodes you would need 1 extra trusted node. (and maybe quite a few more random number generator trusted nodes.)

Remove the idea of sandbox. Remove the idea of trying to make the calculated code closed source.

Eventually have it set up so that the user running the program on their GPU can automatically start hashing again if no computation is available that is worth it.
