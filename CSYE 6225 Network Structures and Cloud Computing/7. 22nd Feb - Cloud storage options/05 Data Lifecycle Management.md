Object stores are good at giving back data as quickly as possible
But over time we want to transition data to other tiers

Most cloud providers allow is to define lifecycle policies that let us define rules that let us mention when to move data to the different tiers. **Data lifecycle policies**

### Object Tagging

Identifying information 

### Cross Region Replication
- Sync between buckets that are geographically spread across
- Pay for service - bandwidth transfer - and the object storage replication

Object stores don't have the capability to search for an object, so whenever we create / update data, metadata is sent back. So it is the user's responsibility to track and organize data on their end. 

### Not suitable for usage as a file system