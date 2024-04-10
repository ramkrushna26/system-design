
## Architectural Design
- macro components (high level design)

## Logical Design 
- business logic - algorithms, databases, work-flows
- extensibility (ex: should be easily able to change database)
  - abstract database layer from application layer (low coupling)
  - ex: payment gateways

## Physical design
- input output, interfaces, storage, processing
- capacity planning, Hardware decisions, UI frameworks, backups & restore, redundency

## Design blogs to read
- zerodha
- youtube
- whatsapp

## how to approach system design
- define scope
- don't over-engineer things - define boundaries/scope

#### Functional scope
- features for the users  
  - ex: follow, tweet, re-tweet  
- input, behaviour & output
  
**something system must have**  

#### Non-Functional scope
- how system should be implemented
- redundency, security, availability, speed, reliability
  
**something that defines & determines systems capabilities**  
  
</br>  
  
**product owners/manager** - talks in terms of functional requirements  
**tech leads, principle engineers** - talks in terms of non-functional requirements  
  
### while designing system
- ask questions
- seek clarifications
- & do not assume

### approaches to building systems
**bottom-up**: build individual components which work together  
  - big MNC can go with it as they know why they are building the system & components features
**incremental**: build MVP(version 0) then add incremental features & complexities to it
  - start-up as they want to see whether product is market fit or not

## Start small & build on top 
- define building blocks (auth, payment, feed, trends services etc)
- define relationship between them (relationship between service, data)
- define communication (how services talk to each other, whether its shared database, message broker, http)
- identify bottlenecks & fix them (scaling system, security)

## while building system, we mostly decide on below components
1. Database - persistent storage
2. caching
3. scaling - horizontal & vertical
4. delegations - for gaining performance out of the system
5. concurrency - using semaphores, mutex, locking to protect critical sections (multi-threading)
6. communication - tcp, udp, http, web sockets, etc
  
**each of the above decisions** will define/determine how your system scales  
