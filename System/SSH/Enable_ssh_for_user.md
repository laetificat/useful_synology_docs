# Enabling SSH for a user
First make sure you have access as root or admin via SSH, [described in this document](Gaining_access_via_ssh.md).  
And you need to enable the [User Home Service](../User/Enable_user_home_service.md).

## Enabling SSH for user
To enable SSH for a user, log in as root on your NAS by using ```ssh root@IP_OF_NAS``` and use the password for your
admin user. (Make sure your admin is enabled and has a password.)  
When you're logged in run ```vi /etc/passwd```, now you should see a list of users and their rights. Learn more about the
passwd file [HERE](https://en.wikipedia.org/wiki/Passwd). Change the ```/sbin/nologin``` to ```/bin/sh``` for the user
you want to enable SSH for.