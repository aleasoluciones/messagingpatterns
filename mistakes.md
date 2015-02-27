Mistakes we made:

 * Use a lot of diferents exchanges / queues. Lot easier to use something like "events" and each process it's queue (with persistence or not, depending on the requirement of the process)
 * Use a python centric serialization. Event worse, python classes serialization. Now we use json and use python and Go.
 * The consumers not prepared for events on previous format versions. The consumers should support the actual and the previous version and not explode with the new version.
 * To much code/stuff on our code (routing, paralelism, and so on). The broker is a better place for high througput routing, load balancing, messages ttl, etc


on doubts, send an event, is free...
