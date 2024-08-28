<!-- Jatin Bunkar Notes For ElastiCache--> 
## ElastiCache

### ElastiCache Simplified:
The ElastiCache service makes it easy to deploy, operate, and scale an in-memory cache in the cloud. It helps you boost the performance of your existing databases by retrieving data from high throughput and low latency in-memory data stores.

### ElastiCache Key Details:
- The service is great for improving the performance of web applications by allowing you to receive information locally instead of relying solely on relatively distant DBs.
- Amazon ElastiCache offers fully managed Redis and Memcached for the most demanding applications that require sub-millisecond response times.
- For data that doesn’t change frequently and is often asked for, it makes a lot of sense to cache said data rather than querying it from the database.
- Common configurations that improve DB performance include introducing read replicas of a DB primary and inserting a caching layer into the storage architecture. 
- Memcached is for simple caching purposes with horizontal scaling and multi-threaded performance, but if you require more complexity for your caching environment then choose Redis.
- A further comparison between MemcacheD and Redis for ElastiCache:
![Screen Shot 2020-06-18 at 8 18 34 PM](https://user-images.githubusercontent.com/13093517/85083820-edc1b480-b1a0-11ea-88b0-15f90bd60282.png)

- Another advantage of using ElastiCache is that by caching query results, you pay the price of the DB query only once without having to re-execute the query unless the data changes.
- Amazon ElastiCache can scale-out, scale-in, and scale-up to meet fluctuating application demands. Write and memory scaling is supported with sharding. Replicas provide read scaling.
