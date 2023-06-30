Enable root Access for Linux Instances
AWS doesn't grant root access by default to EC2 instances. This is an important security best practise. Users are supposed to open a ssh connection using the secure key/pair to login as ec2-user. Users are supposed to use the sudo command as ec2-user to obtain elevated privileges.

Problems arise with a number of software packages which require remote root access for installation and operation. The following cheat sheet explains how to enable root access. It hasn't been tested with all Linux distributions.
Disclaimer: Enabling direct root access to EC2 systems is a bad security practice which AWS doesn't recommend. It creates vulnerabilities especially for systems which are facing the Internet (see AWS documentation).
Use these commands on your own risk. Understand the function of the commands and the related risks before you apply them.
All commands require root privileges which can be obtained through the `sudo` command.

Create a root Password
```
$ passwd root <the password>
```

Configure and Restart the `ssh` Service for root Access
Edit the configuration file `/etc/ssh/sshd_config.` Change the following to parameter to the values shown below:
```
PermitRootLogin yes
PasswordAuthentication yes
```
Restart the service with the command
```
$ service sshd reload
```

Patch the authorized Keys File for the root User
The simplest way is to use the ec2-user file and the certificate for the root user. Copy the ec2-user file over to the root user:
```
$ cp ~ec2-user/.ssh/authorized_keys ~root/.ssh/authorized_keys
```

This allows as well to login with the same key which is available for the ec2-user.

Update the AWS Cloud Configuration File
Edit the file /etc/cloud/cloud.cfg and change the following entry to this value:

disable_root false
