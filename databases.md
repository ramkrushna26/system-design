1. in-memory (caching)
2. disk based
3. server'rd
4. embeded
5. row-based
6. columnar
7. graph db
8. tim series
9. relational
10. non-relational
11. blob storage
12. flat file storage
13. storage for text based search (elastic search)
    
</br>  

Example:  
**users**  (Id, name, bio)  
**blogs**  (Id, title, user_id, published_at, is_deleted, body, excerpt, slug)   
**tags**  (Id, name)  
**blog_tags**  (blog_id, tag_id)  

</br>  

**excerpts**: few words from blog body for search (summary of blog)  
**slug**: short url for blog  
  
</br>  

- **Hard delete** --> your database had to do lot of disk I/O in case of hard delete and it will delete a row and sql has to re-balance the B+ tree  
- **Soft delete** --> you can mark row as soft delete, handle it on application side. and non-business hours run batch job to delete such records.

</br>
  
- Should we store body of the blob in the database?  
    - few Kb of rows should be okay if database size is small  
- storing images & huge blob in tables, your database will take **performance hit**  --> use blob storage, and store reference to it in database table

</br>  

- **integer** comparision is much **faster** than string comparision
- for datatime fields/object, use **epoch time or yyyymmdd (int)** type --> to get most performance out of your databases as comparing datatime/date objects is costly/take highr time
- **for handline timezone difference, store datetime in utc** in database, convert on-fly according to users timezone while showing it to user

</br>

### Read below 
- Database redundancy (Standby, 1:1, N:N)
- storage redundancy (RAID, geo redundancy, data centre redundancy)

</br>

## Relational Databases
- Rows & columns
- relations -- 1:1, 1:N, N:N
- Normal Forms: 1NF, 2NF, 3NF and so on
- contraints on columns or combination of columns (unique, not null, primary key, foreign key)
- Trasaction: (ACID)
    - Atomicity
    - Consistency
    - Isolation
    - Durability

</br>

### Assignments
- implement/simulate transaction isolation
- implement transaction durability -- handle system failure
- build trigger framework
    - define trigger on data & conditions

### Databased Indexes
- improve lookups performance
- decreases write performance
- B+ tree data structure used for indexes
- index is small table containing two columns

#### Types of Indexes
- primary index : key + address of data
- cluster index : key + data ---- order by key
    - huge boost in perfromance
    - reordering & updates are expensive ----as every write has to synchronously update the indexes
- secondary index
- composite index
- partial index

</br>

- you can specify which index you want to use while running a query -- certain DB provide such functionality

## Database Locking

### Read lock/Shared lock
- records are reserved for read by current session
- other session can read the locked data
- other session can NOT update/write locked data

### Write lock/Exclusive lock
- records are reserved for write by current session
- other session can NOT read/write the data

</br>

- **lock granularity**: table, rows, columns
- page level locking

</br>

- if engine detects deadlock then it kills the session/transaction running which the deadlock was detected

</br>

- database meant handle locking and ensure persistant data, so don't handle locking on application side, it will make things slow

```
AUTOCOMMIT OFF;

SELECT *** FOR SHARE; #To get the shared/read lock

SELECT *** FOR UPDATE; #To get the write/update lock
```

</br>

Skip rows if they are locked:
- If a row is locked by transaction then other transaction requesting same rows must wait until the lock is release.
- **NOWAIT**: query executed and failed if rows are locked
```
SELECT * FROM TAB WHERE ROW = 3 UPDATE NOWAIT;
```

- **SKIP LOCKED**: removes locked rows from result set
```
SELECT * FROM TAB WHERE ROW = 3 UPDATE SKIP LOCKED;
```

## 
















