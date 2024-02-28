- Similar to what we have on local machine - different OS comes with different file systems FAT32, NTFS, ext3, ext4 XFS ...
- A block is the minimum amount of data that can be read form a system
- All interactions with block level storage happens through the OS
- Can be persistent or ephemeral - RAM ? 

### Categories 
1. Network attached storage
2. Instance Storage

When we create a new instance on google cloud / amazon - all the various options available are block level storages. All VM discs are not on the same physical server. 

To enable stateless VMs, we can use EBS volumes ( AWS ). 

	 When we deleted instances using tf destroy the instances deleted but the disk still remains around as they are at a network level and not at the instance level

!!! Delete all discs that were created while working on assignments. 

Each disk can only be attached to one VM at a given time. 

### Availability

Backups - replicas are created in the same zone as the one where the disk lives. Whenever there is hardware failure, network traffic is directly routed to the backup. While we don't pay for it explicitly, it is baked into the pricing model. 

### Snapshot

Snapshots are automatically taken once a day by cloud vendors, ( included in pricing ). Deleted when we delete the disk. 

- Manual snapshots cost money, but won't be deleted when we delete the disk. 
- Subsequent snapshots only store the delta between the prev snapshot and the current state- this way the cost is low

### Encryption

Amazon EBS encryption provides a seamless support for data-at-rest and data-in-transit between EC2 instance and EBS volumes. 

However, this increases latency because of the encryption and decryption process when reading and writing data. 

### Instance Store

While network attached disks are the default option. Since the bandwidth is shared by all the different VMs that are on a machine, it is not suitable for high network requirement work loads. 

Instance store is a temp block level storage that are physically attached to the host computer. However, we can't this on all types of machines. Because if it is  physically attached to the machine, the cost will get inflated. 

While the instance store is restarted or rebooted, the data persists, however this is deleted whenever the instance is deleted or terminates. 
##### Payment
The storage is changed as long as it is attached to this instance. We have to work with an assumption that we will lost the data at any given moment if the instance gets terminated / stopped. 

Use only for workloads that have cached data, which can be rebuilt, just for ephemeral workloads which need fast access to data maybe like a RAM. 



