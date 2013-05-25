CompuShare
==========

A program to be used by "workers" that will either hash or run "pay-per-iteration" Monte Carlo simulations depending on which pays higher at the time. 

Would result in a worldwide "distributed supercomputer" which runs GPU optimised code.


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

This worker client is what will be called CompuShare.
