### Approaches
1. Optimistic - Very few ops happen on the same record, so why pay penalty of throughput . However we are going to have safeguards in place to stay ACID compliant - Trust but Verify
2. Pessimistic - Block an operation of a transaction if it may cause violation of the riles until the possibility of violation disappears - affects performance

### Write-Write Conflict
- Two users updating same data item with different values
- Optimistic Approaches: 
	- Conditional Update : see if value has changed since last read before update
	- Go ahead and write it, but mention that there is a conflict

### Read - Write conflict
- Someone else buys the one available ticket before you finish your payment process

### Version Stamps
 ????

#cloud-important vacuum in postgres
The more we vacuum, the slower it gets. This is the garbage collection process that happens in databases. Could be older versions of records.

### Sharding ???
- #cloud-important Picking the key on how you shard the data is extremely important

### Primary / Secondary Nodes Replication (Distributed Model)

### Peer to Peer Replication ( Distributed Model )
