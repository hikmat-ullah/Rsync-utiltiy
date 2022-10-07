# Rsync-utiltiy in Linux

Rsync is a utility for efficiently transferring and synchronizing files and directories within same computer or to a remote computer by comparing the modification times and sizes of files.
Rsync is a lot faster than ftp or scp.

This utitily is mostly used to backup files and directories from one server to another.

The default port for this utility is 22 ( same as SSH )

## How to install rsync utility on linux machine or server

### yum install rsync // on centos 7 or redhat 

### apt install rsync // on ubuntu machine

### rsync a file on a local machine

// create a tar file of entire home directory
 
cd /home/hikmat

tar cvf backup.tar . // here dot means current directory at the end of command 

rsync -zvf backup.tar /tmp/backups // Create backups directory if it is not created or present

### rsync a file on a remote machine
This is send a file named backup.tar from local server to remote server.

mkdir /tmp/backups // create directory on a remote server

Now run this command to send a file to a remote server

rsync -avz backup.tar hikmat@192.168.1.x:/tmp/backups

### Rsync file from a remote server

rsync -avzh hikmat@192.168.1.x:/home/hikmat/backups.tar /tmp/backups

The above command means that the file backups.tar is already existed on the remote server 

