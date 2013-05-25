CompuShare
==========

A program to be used by GPU bitcoin miners "workers" that will either hash or run "pay-per-iteration" Monte Carlo simulations depending on which pays higher at the time. 

Would result in a worldwide "distributed supercomputer" with focus on GPU optimised code.


Stage 1
==========
Build a "simple" Monte Carlo iteration for the use on a phantom in a clinical setting using WebCl through [Nokia's plugin](http://webcl.nokiaresearch.com/extensions/firefox/multiplatform/latest/webcl-1.0.xpi) in [Firefox 21](http://www.firefox.com/).

Stage 2
==========
Implement this on a website so that anybody can go to the website, run the javascript code and it would automatically add iterations to the result.

Stage 3
==========
Implement a method of payment through Bitcoin.

Stage 4
==========
Make a "worker" program in which the user can add a list of trusted websites that run on WebCl and contain payment in Bitcoin. The code would default to the WebCl Bitcoin miner written by [Adrien Plagnol](https://bitbucket.org/dalsh/jsoclbm) if all else failed.
