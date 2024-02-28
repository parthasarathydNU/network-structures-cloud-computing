Start using cloud sql instances.
I need to create the env file  - start up script / cloud init

In terraform metadata tag - 
Have a script that get's executed when instance is launched

Amazon executes it once when machine is launced - 
google executes it once whenever machine restarts - this will be a problem in our assignment ( idempotent way )
Check if file exists if not go ahead and create it and place it

we can check system logs we can check a particular file that professor will mention once he figures that out. 

We have to enable private services access - under vpc to ne able to use google cloud cloudsQL instance

just add the extra part in the terraform file, try to see manually if we are able to createa Cloud SQL instance. if not there is some issue with the TF file. 

Disable delete production for this assignmnet when we create a cloud sql. 

Disable automatic storage scaling - seleect the cheapest storage

instance names cannot be reused for 7 days in google cloud - so use the random string generator provider by terraform to work with this. If we need to debug the database, we will ssh to the vm instance and talk to the database through that.

We no longer will require a local database - must use cloud sql database
No public IP, not internet accessible
Only application can talk to database server