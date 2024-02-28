
### Characteristics

- Schema-less
- Does not use relational model
- Runs well on a cluster / horizontal scaled setup
- Free of joins - no relationship between data
- Schema need not be explicitly defined in the database

### More than rows
- Key Value (Dynamo DB, Redis)
- Graph
- Column-Family (Cassandra)
- Document (MongoDB, FireStore, Dynamo DB)

#### Key Value Store
- key is always a string, the value can be any data that is represented as a blob

#### Graph Databases
- Data whose relations that are well represented as a graph consisting of elements of interconnected elements
- Social relations, public transport links, road maps or network topologies


### Tradeoffs
- Additional logic has to be added in application tier code 
- Work of keeping data consistent is now moved to the application layer

### CAP Therm

It is impossible for a distributed system in presence of a network separation to simultaneously provide more than two of three of the guarantees: 
- ***Consistency*** - Every read receives the most recent write (or) an error
- Availability - Every request receives a (non-error) response - without guarantee that it contains the most recent write
- Partition Tolerance - If packages are dropped, the system continuous to operate. #cloud-important  This is where the split brain problem in distributed systems come into play

**Example:** in instagram we don't know when people actually clicked the like button, but how many likes they have. So here availability is more important than consistency

#cloud-important  Consistency in CAP theorem is quiet different from what is guaranteed in ACID. - this is the concept of [Eventual Consistency](obsidian://open?vault=Notes&file=Advanced%20Big%20Data%20Indexing%20Techniques%2FClass%20Notes%2FClass%203%20-%20Rest%20APIs%20and%20keyvalue%20stores%2F03%20Distributing%20the%20data)


