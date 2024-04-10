- locality of reference
- **recent data** most likely to be accessed
- cache **reduces disk I/O & network I/O**

</br> 

- maximize **cache hit**
- minimize **cache miss** --> cache miss are expensive

</br> 

- **application server cache**: request layer cache
  - caching happens on your API server
- **centralized cache**: redis, memcached
- **central & distributed cache**: sharded data using centralized cache
- **CDN level caching**: geographically closed caches for geographically spread application (cloudfare, akamai)

</br>

- cache **seats next databases** for seamless access & transaction

</br>

- disk cache
- cpu cache
- gpu cache

</br>

### cache eviction policies 
- FIFO : first in first out
- LIFO : last in first out
- LRU : least recently used
- MRU : most frequenctly used
- LFU : least frequently used
- RR : random replacement
  
**& how to implement them?**  

</br>

## Types of caching
### 1. write through cache
- write to db & write to cache
- both write pass then write pass
- data present at both places everytime
- **pros**: fast retrievals, data consistency, fault tolerant
- **cons**: higher write latency

### 2. write around cache 
- write to db but no write to cache
- good for applications that do not read immediately after write
- **pros**: not flooding cache with unused writes
- **cons**: recently written records will be cache missed
  - higher read latency (first read)

### 3. write back cache
- write to cache & I/O done
- data written to db in background
- **pros**: low latency, high throughput & write intensive application
- **cons**: data availability risk 


## CDN (Content Delivery Network)
- get content from closes available server instead of getting from main server
- improve speed by keeping content close to users
- security (delegate to cdn) -- DDoS, rate limiter

</br>

**cons**  
- dirty content serve to users if cache invalidation does happen
  - you have to either invalidate the cache explicitely or set TTL
- caching policies & configurations

</br>

**What content could you store in CDN?**  
- data that does **NOT** change often
  - videos, images, text, API

### Caching at various levels
- DNS
- API Server (in-memory) (on-disk: reduces network I/O)
- Client side
- Pre-computed (Materialized Table Views)
- Load balancer
- Centralized cache
- Transperant cachec in front of DB (ex: CachOps)
- API Gateway cache

</br> 

- Read about ---- DB Buffer pool
