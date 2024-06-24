!. How to share file using ip address.
1. $ rsync -rac <filename> <username>@ip_address:<destination_path>


2. Create a Linux launcher icon.
$ vi /usr/share/applications/<application_name.desktop>



How to check current default permission?
$umask


chomd: change permission the file
chown: change user/owner permission
chgrp: change group permissioin


if you change the permission inside the folder all files so-------->
chmod -R user:group <folder_name>

if you change 1 file permission so ------>
chmod -r user:group <file_name> 

chown -c devendra 03-file 
chgrp -c devendra 03-file

-------acl commands
getfacl 03-file 

adding permission for user-
setfacl -m u:user:rwx <file_name>

adding permission for group-
setfacl -m g:user:rwx <file_name>

remove a sacific entry-
setfacl -x u:user:rwx <file_name>

remove all entries-
setfacl -b <file_name>

adding permission for user in all the files inside a folder
$setfacl -Rm "entry" <target_file/folder>

Composer----------->
https://www.cherryservers.com/blog/how-to-install-composer-ubuntu


Install secure phpmyadmin--------->
https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-phpmyadmin-on-ubuntu-20-04

How to install and configure phpMyAdmin------->
https://ubuntu.com/server/docs/how-to-install-and-configure-phpmyadmin

how to create toa  user?
useradd <usre_name>
adduser <user_name>

useradd -g <group_name> -s /bin/bash -c "This is a tempory user" -m -d /home/<user_name> <user_name>


Modify user-----
root@wadmin-Veriton-M200-H310:/home# id alex
uid=1003(alex) gid=1003(alex) groups=1003(alex)

# Change the default group 
root@wadmin-Veriton-M200-H310:/home# usermod -g demo alex

root@wadmin-Veriton-M200-H310:/home# id alex
uid=1003(alex) gid=1005(demo) groups=1005(demo)

root@wadmin-Veriton-M200-H310:~# usermod -g devendra dev
root@wadmin-Veriton-M200-H310:~# id dev
uid=1002(dev) gid=1001(devendra) groups=1001(devendra)

# add new group but default group also there 
root@wadmin-Veriton-M200-H310:~# usermod -G demo dev

root@wadmin-Veriton-M200-H310:~# id dev
uid=1002(dev) gid=1001(devendra) groups=1001(devendra),1005(demo)


Other usermod options:-------->
-m -d :- /home/newfolder (to move the content of home folder to this new folder)
-p : we can use passwod command also 
-L -U : Lock/Unlock a uer

root@wadmin-Veriton-M200-H310:/home# ls
alex  dev  deva  devendra  wadmin
root@wadmin-Veriton-M200-H310:/home# mkdir alex/demofolder
root@wadmin-Veriton-M200-H310:/home# ls
alex  dev  deva  devendra  wadmin

root@wadmin-Veriton-M200-H310:~# usermod -m -d /home/alex_a alex
root@wadmin-Veriton-M200-H310:/home# ls
alex_a  dev  deva  devendra  wadmin
root@wadmin-Veriton-M200-H310:/home# cd alex_a/
root@wadmin-Veriton-M200-H310:/home/alex_a# ls
demofolder

root@wadmin-Veriton-M200-H310:/home# usermod -m -d /home/alex_x alex
root@wadmin-Veriton-M200-H310:/home# ls
alex_x  dev  deva  devendra  wadmin
root@wadmin-Veriton-M200-H310:/home# cd alex_x/
root@wadmin-Veriton-M200-H310:/home/alex_x# ls
demofolder


Q. Difference between update & upgrade?

UPDATE: keep the old packages, we can rollback.
UPGRADE: will delete the old packages.


if you create a folder inside the folder using one command 
$ mkdir -p <folder1_name>/<folder2_name>


Use set-hostname to Change the Hostname
$ hostnamectl set-hostname new-hostname

### What is Systemd?
1. Systemd is a software suite that provides an initialization system and service management for Linux operating systems.
2. Systemd is the first process started by the Linux kernel (with PID 1).
3. It initializes and configures the userspace environment and services.
4. Services are defined in unit files, which describe how to start, stop, and manage each service.
5. Systemd uses socket-based activation to start services on demand when a request comes in.
6. It also provides features like on-demand starting of daemons, parallelized starting of services, and automatic restarting of crashed services.

## Key Components of Systemd
1. systemd: The main daemon that manages the system
2. systemctl: The command-line tool to control the system and service manager
3. journalctl: The tool to view and query logs managed by the systemd journal
4. systemd-analyze: The tool to analyze system boot-up performance

## Benefits of Systemd
1. Faster boot times: Systemd can start services in parallel, leading to faster boot times.
2. Improved dependency management: Systemd can automatically start required services based on dependencies.
3. Better logging: Systemd provides a centralized logging system called the journal.
4. Easier service management: Systemd provides a consistent way to manage services using systemctl.

```
$grep
```
The name "grep" comes from the ed (a Unix line editor) command g/re/p which means “globally search for a regular expression and print all lines containing it”.
