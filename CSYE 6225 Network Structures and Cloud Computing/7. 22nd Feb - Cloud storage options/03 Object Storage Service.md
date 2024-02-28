When dealing with files, prefer object storage service. 
This shifts the compute power and all the operational overhead to the storage server. 
And all file upload and download operations are processed on the storage server. 
However all these are charged. While we can control the number of requests, and file sizes, we cannot control the bandwidth. Money is charged for data flow in and out of the object store. 

Example: if someone pays a 100K a month, around 50K is paid towards the object store. 

### Amazon S3 / Google Cloud Storage

- Every object has metadata and the actual data. 
- There are few operations where we can just work with the metadata, this is where HTTP methods such as HEAD and OPTIONS come into the picture - cost saving
- Any thing can be stored here, pdf, movie, audio, random binary data, ....
- Object Store on S3 is the oldest service
- Max size of a single object that can be stored is 5TB

### Unique

- Unlike other storages, we only work with object stores through HTTP requests. 
- We don't need VMs to work with this
- We cannot mount it to the VM unlike Block Level Storages of Elastic File Storages or NFS file share

### Data Consistency Model for S3

- Objects are immutable in object storage, whenever we update a file, the newer file replaces the older file rather than rewrite it in place
- It might be possible maybe on local storage, but when we are interacting with the OSS through REST APIs, objects are immutable
- **All operations on S3 are strongly consistent**

In eventual consistency model, the workaround to enable strongly consistency is to always create a new version of an object when there is an update operation. There might be some issues in getting older data when fetching an existing object after update, but we always get the latest one when we create a new object. 



### S3 Storage Tiers
