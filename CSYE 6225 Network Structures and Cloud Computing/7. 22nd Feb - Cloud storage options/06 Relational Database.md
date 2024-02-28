The idea - store data in tabular format and maintain relationships between entities
Based on mathematical concepts of relational algebra

Selecting a RDB depends on the technical requirements of the workload

### ACID - Atomicity Consistency Isolation Durability

In order for a database to be called relational it has to be ACID compliant. 

##### Atomicity
- Transitions have to have all steps execute successfully or consider all as failed.
- All steps in the process are considered as one unit ( atom )

##### Consistency
- A transaction will bring the DB from one consistent state to another

##### Isolation
- Ensures that concurrent execution of transactions results in a system state that would be obtained if each of those transactions were executed sequentially
- Each database can have various storage engines, and each can handle the isolation process differently - some lock the entire row, entire table or just a cell
- This granularity of isolation defines the number of concurrent operations that can happen on the DB

##### Durability
- A transaction once committed must remain committed even in case of power loss, crasher or errors
###### How do database systems ensure transactions are protected even if power loss or crashes or errors ? How is durability ensured ?

#cloud-important 
Write ahead logs - as you commit a transaction, we log the transaction async. When we backup a data base it is also important to backup the write ahead log. 

When a data is brought back up, it first replays the write ahead logs and then uses the backup data to check if everything is in sync.

The length of write ahead logs. that we have sort of play into the disaster recovery plan. 






### Automated Backups of AWS RDS

#cloud-important 
In addition to snapshots that we take, there is an option to enable point in time recovery for a database. This costs money, because additional logs are required to recreate a database at any given point in time. 

### Restoring Backups
On cloud all restore options will result in a new instance with a new host name. 

### Multi AZ deployments

A limitation that all off the shelf databases have is that while we can read from multiple instance, we can only write to one instance. So the only true way to scale a database, is vertical scaling. 

We have one instance on active, and the other on standby. This is the default option that is used when we spin up  dbs on cloud platforms. Standby and active instances are synced. 

If there are too many transactions the standby might lag behind the active. But incase standby is not that far away from active, the backup and snapshot ops are run on the standby. 

Upgrade operations are run similary, first standby is upgraded, promoted to active, and then active is upgrades when it becomes the standby




### Read Replicas

#cloud-important 
These days, there are more number of reads as compared to writes. This is the concept of read replicas. All fetch queries go to the read replica, all other insert and update queries go to the active instance. 

Read replicas will always be in lag, however when we request data, the db knows what is lagging, it will not fetch data for you, because we don't want to give stale data back. Sometimes the lag will get so bad that the read replica will never recover, so we have to decommission it. 

This is where monitoring systems come to place which help us. 

When we scale up, we move to a cluster model where each node has a primary and multiple read replicas. 
### Issues with distributed systems 

Storing the same data in multiple instances of databases with auto incrementing keys are an issue. Because if they go out of sync, it becomes and issue when we want to reconcile the data / recover the data

## Value of Relational Database

- Everyone knows SQL. 
- Every NoSQL database out there, when they got serious users they had to support legacy users.
- ACID compliant
- Store large amounts of persistent data

Throughput in a system increases, when we stop relying on transactions - stop rely on ACID compliant. 

## Issues with RDBMS

- Mediocre horizontal scaling support
- Select queries make full table scans
- #cloud-important read about how an index is important in a RDBMS
- Mismatch on how the data is stored an how it is actually used in the app tier - example for coming up with one person object, values from multiple tables need to be read and merged



