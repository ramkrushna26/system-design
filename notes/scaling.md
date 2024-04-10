**Number of requests system can handle simultaneously.** [adding resources to infrastructure]  

</br> 

## Vertical scaling
  - (Hulk): Make your system bulkier by adding more CPU, RAM, DISKs, etc.
  - your system hits limit at certain points so limted capacity
  - **scaling up**
  - cost is high due to heavy configurations (resource will be of waste when traffic is less, cost is always high)
  - % of traffice is affected more during down
  - SPOF (Single Point Of Failure)
  - infinite scaling is not possible
  - Geo-latency optimization is not possible

### Vertical scaling: Advantages
  - Low licensing fees
  - easy implementation
  - just one system to manage

### Vertical scaling: Disadvantages
  - limited scaling
  - risk of complete downtime
  - outage due to hardware failure

</br>

If you are building product from scratch then go with vertical scaling with some extent, then based on need, transition to horizontal scaling.  

</br>  

## Horizontal scaling
  - (Minios): Add more instances to distribute load across multiple systems
  - capacity is more as multiple system are combine to handle load
  - **scaling out**
  - can use cheaper hardware as when its needed, so cost is low
  - % of traffic is affected less during down & code should be backword compatible
  - No SPOF
  - infinite scaling is possible 
  - Geo-latency optimization is possible

### Horizontal scaling: Advantages
  - Easy scaling
  - linear amplification
  - easy forecasting
  - fault tolerance
  - easy deployment
  - cheaper
  - resilience
  - infinite scale

### Horizontal scaling: Disadvantages
  - complex architecture
  - licensing fees is more
  - bigger footprint
  - networking & partitioning

</br> 

- For horizontal scaling, in most cases we need **load balancer**
- Based on task type (memory, CPU intensive), your load balancer can split the traffic to handle such cases
- load balancer is set of multiple machines, to avoid being single point of failure

</br>

- When you horizontally scale your system, make sure your **database/cache support those many concurrent requests**
- or any other shared resource that your application might be using (database/cache/elastice search/aws service) should support those many concurrent users

## Scaling Databases







