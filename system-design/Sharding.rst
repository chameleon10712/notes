Sharding
============

.. image:: https://camo.githubusercontent.com/1df78be67b749171569a0e11a51aa76b3b678d4f/687474703a2f2f692e696d6775722e636f6d2f775538783549642e706e67

Sharding distributes data across different databases such that each database can only manage a subset of the data.  Taking a users database as an example, as the number of users increases, more shards are added to the cluster.

Similar to the advantages of ``federation``, sharding results in less read and write traffic, less replication, and more cache hits.  Index size is also reduced, which generally improves performance with faster queries.  If one shard goes down, the other shards are still operational, although you'll want to add some form of replication to avoid data loss.  Like federation, there is no single central master serializing writes, allowing you to write in parallel with increased throughput.

Common ways to shard a table of users is either through the user's last name initial or the user's geographic location.

Disadvantage(s): sharding
--------------------------

- You'll need to update your application logic to work with shards, which could result in complex SQL queries.
- Data distribution can become lopsided in a shard.  For example, a set of power users on a shard could result in increased load to that shard compared to others.

  - Rebalancing adds additional complexity.  A sharding function based on `consistent hashing <http://www.paperplanes.de/2011/12/9/the-magic-of-consistent-hashing.html>`_ can reduce the amount of transferred data.
- Joining data from multiple shards is more complex.
- Sharding adds more hardware and additional complexity.

Source(s) and further reading: sharding
-----------------------------------------

- `The coming of the shard <http://highscalability.com/blog/2009/8/6/an-unorthodox-approach-to-database-design-the-coming-of-the.html>`_
- `Shard database architecture <https://en.wikipedia.org/wiki/Shard_(database_architecture)>`_
- `Consistent hashing <http://www.paperplanes.de/2011/12/9/the-magic-of-consistent-hashing.html>`_

|

`[ref] <https://github.com/donnemartin/system-design-primer#sharding>`_



|

List
-------

- `MongoDB Sharding 分散式儲存架構建置 (概念篇) <https://blog.toright.com/posts/4552/mongodb-sharding-%E5%88%86%E6%95%A3%E5%BC%8F%E5%84%B2%E5%AD%98%E6%9E%B6%E6%A7%8B%E5%BB%BA%E7%BD%AE-%E6%A6%82%E5%BF%B5%E7%AF%87.html>`_





