
- What does not need to be done in realtime --> **should not be done in realtime**
- delegate whatever task at hand & respond

</br>  

- In most cases, your analytical fields are pre-computed
- example: like counts on vidoes/image/post, **need not be done in real time**, you can store and then through batch process you can update in DB
- **LAG** : processing of task, when it is submitted to message broker and updating in database ----> **this lag should be minimal**
  - monitor the lag: set up alerts
- 
 
</br>   

### Message Queue
- contains serialized task contains necessary task details
- FIFO or close to FIFO  ----- choose depend on your use case
- **Features of Queue**
  - Expiration Date (message expiration date)
  - delay
  - at most once
  - at least once
  - exactly once
  - wait until message retrieved
  
</br>   

**What would user interface look like where there are async task?**  
- provide false sense of completion --- (Ex: provide task id and status)
- ex: followers count ++
  - update local copy --- immediatly
  - db update --- async
 
</br>   

**Two Common Implementation**  
### 1. homogenous consumers
- message queue
- SQS, RabbitMQ, Redis, etc.
- **Every consumer does the exact same things**. So, every message cab be consume by any consumer/workers

</br>   

### 2. heterogenous consumers
- data queue
- kafka, kenesis (event driven architecture)
- one message can be consume by one or many consumers as each consumer has been implementated with seperate logic
- 














