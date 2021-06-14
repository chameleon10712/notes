Thread Level Parallelism
=============================

|

Thread Throttling
---------------------


When a large number of users attempt to synchronize simultaneously, 
the load on a single server can become excessive. 
Thread throttling significantly reduces the total number of simultaneously active transaction processor threads and database extraction threads, 
thereby increasing the overall throughput for synchronization, without reducing the number of concurrent users. 
Synchronization performance degrades slightly but will successfully complete for all users.


Thread throttling allows the maximum possible number of concurrent users. 
It throttles in a manner that maximizes application server usage during any mixture of transaction processor and database extraction threads. 
Thus, if the server supports x concurrent transaction processing threads, 
it will allow this number of transaction processing threads while disallowing all database extraction threads. 
Similarly, if the server supports y concurrent database extraction threads, 
it will allow this number of database extraction threads while disallowing all transaction processing threads. 
If fewer than x transaction processing threads are currently active, 
some database extraction threads are allowed to execute concurrently. 
Similarly, if fewer than y database extraction threads are currently active, 
some transaction processing threads are allowed to execute concurrently.


