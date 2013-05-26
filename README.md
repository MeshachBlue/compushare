Project Name Change
==========
Due to the name CompuShare already in use, this project is now known as The Distributed GPU Project and is available at:
https://github.com/MeshachBlue/DistributedGPU

Overview
==========
Should all of the following 4 steps be completed successfully this would result in a worldwide [distributed computer](http://en.wikipedia.org/wiki/Distributed_computing) which runs GPU optimised code. Researchers could implement this code on their website, anyone who went to this section of their website would be able to run their code and return results. Eventually the researchers would end up competing for the general public's computation time in an auction style.

A worker client would be made available based on [Bitcoin](https://www.weusecoins.com/en/) transactions that would accept these computation requests in return for being paid in Bitcoin. This worker client would default to running a "Bitcoin miner" if nothing more profitable was available.


Stage 1
==========
Build a "simple" [Monte Carlo](http://www.crcpress.com/product/isbn/9781466507920) iteration for the use on a [phantom](http://en.wikipedia.org/wiki/Imaging_phantom) in a clinical setting using javascript [WebCl](http://www.khronos.org/webcl/) through [Nokia's plugin](http://webcl.nokiaresearch.com/extensions/firefox/multiplatform/latest/webcl-1.0.xpi) in [Firefox 21](http://www.firefox.com/).

The exact nature of this Monte Carlo simulation may vary depending on what is most useful to my supervisor.

Stage 2
==========
Implement this on a website so that anybody can go to the website, run the JavaScript code and it would automatically add iterations to the result.

At this point the code would be useful to researchers. They could ask friends, family and co-workers to go to the website and help significantly speed up their code.

Stage 3
==========
Implement a method of payment, preferably through Bitcoin. Other researchers could take this idea and implement other payment/credit systems should they wish. Or simply rely on donated computer time.

Stage 4
==========
Make a "worker" program in which the user can add a list of trusted websites that run WebCl iterations and contain payment in Bitcoin. The code would default to the WebCl Bitcoin miner written by [Adrien Plagnol](https://bitbucket.org/dalsh/jsoclbm) if there were not more profitable computations.
