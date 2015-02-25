Then main thread of execution do the minimal work and put the rest of the work in a queue to be executed async.
There are one or more workers for execute this kind of workloads.
The message system can be loadbalance between the diferent workers.

This is the most tipical use case of messaging on a web environment. There are products for this kind of work distribution.
