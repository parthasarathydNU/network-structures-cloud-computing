
#cloud-important 
In the older days web applications, legacy applications, built before the cloud, they required something like NFS share that let applications quickly switch storage locations. 

So if we want those customers, to move to the cloud we need to provide a solutions, so that's why AWS has pioneered the **EFS**. 

It is highly available and durable because it stores data and metadata across multiple AZs in a region. 
- As we add data, disk grows and shrinks automatically. 
- It supports NFS versions 4 and 4.1. However this has not been built by google. 
- While EBS is zonal, EFS is a regional resource. 

EFS is always a secondary disk attached to a VM and not the primary one. OS cannot run out of EFS. Mounting an EFS store can only be done from inside the VM and not while bringing up the VM. 
