
go back [[3. 25th Jan '24 Thursday#Linux File System]]

#cloud-todo 
- Find out how to check details about kernels when working with the shell.
- Check out link about linux file system in class slides and get the file system diagram
- Check out permissions and flags in linux FS

### Directories in Linux Kernel

- `/bin` - binaries that you can run - commands that we run on the shell
- `/sbin` - bin for super user
- `/boot` - Don't touch it
- `/dev` - Device files - generated at boot time or even on the fly (virtual directory, do not use this for applications)
- `/etc` - system wide configurations stay here. Initially this was used as dumping ground for files that people were unsure where to put. But now it is used for config files. Everything To Configure
- `/home` - user's personal directories - Mostly for human users. System users may not always have a home directory. Nothing should run out of `/home` on a server.
- `/lib` - installed libraries
- `/media` - where external storage will be mounted when you plug in in like pendrive etc..
- `/mnt` - where additional disks are mounted - not used often these days - where we mount storage devices or partitions .. not sure, haven't used
- `/opt` - Use this when we install applications
- `/proc` - contains info about process information (virtual directory) - don't write to proc as this is not persistent
- `/root` - home dir of super user, don't use this
- `/run` - (virtual dir) temp dir for applications that are running
- `/sys` - virtual dir - contains info regarding devices connected to the computer
- `/tmp` - temporary dir for any user to use . This is cleared on each boot. Software / scripts should not be executed from here
- `/var` - used by applications running in the system. it has many directories, popularly `/log`

#cloud-important
- File names and commands in linux are case sensitive
- Linux has no concept of file extension

Food anything you have ? stomach sound making

#cloud-cool
`cd -` is the command that takes you to the previous directory. This is very useful when we have to keep switching between two directories

### Links


#cloud-todo 
Check out hard links and symbolic links.