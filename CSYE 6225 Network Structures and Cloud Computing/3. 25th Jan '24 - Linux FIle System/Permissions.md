go bacl [[3. 25th Jan '24 Thursday#Permissions]]
There are Octal, Binary and File mode for representing permissions. 

The permissions are 
r - read
w - writre
x - execute

- **Read** is represented as `100` in binary, which is 4 in decimal.
- **Write** is `010` in binary, which is 2 in decimal.
- **Execute** is `001` in binary, which is 1 in decimal.

This is how the numbers 4, 2 and 1 came up to be.

### The sudo command

- sudo - super admin user. To be able to use the sudo command, the user has to be a member of the super admin group. 
- the sudeoers file has this information
- There is also a way to limit users to the type of elevation that they can get to

### The su command

Switch user / switch user with login `su [[-l]] userName`. The `-l` flag opens the login screen for that user.

- the `/etc/pwd` file has information about all users in the system
- Here we see that the last part of the entry to show the shell the user uses. 
- For some users we see that the shell is /usr/bin/false. For these users we can use the `su` command to switch
![[Pasted image 20240125203233.png]]

### The kill command

We should not always default to the `kill -9` command. 

Databases though they receive the data, do not immediately commit the data to disk. There are some changes in memory or in cache that are yet to be committed, so if we perform the kill -9 on this database we will miss the data that is yet to be committed. But if we use the normal kill command, it will give time to the DB to perform all the clean up tasks and exit gracefully.

### Shutdown - Poweroff or Reboot

shutdown command will terminate processes in orderly fashion before powering off the system.
`sudo shutdown -r now` - reboot the system

Usually VMs are not rebooted, they are replaced. 