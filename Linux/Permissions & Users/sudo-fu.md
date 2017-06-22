# Sudo-fu
author: Arseny

levels:

  - basic

  - advanced

  - medium

type: tetris

category: tip

---
## Content

Does the command need to be run under root user, or can the command be run with regular user permissions?

Assume all default or conventional unix directories have default set of permissions.

---
## Game Content

sudo:no sudo
```true

ls /usr
```
```false
touch /usr/bin/script
```
```true
touch ~/script
```
```false
pip install ansible
```
```true
pip install --user ansible
```
```false
rm -rf /usr/bin/*
```
```false
rm -rf /usr/local/bin/*
```
```false
ifconfig en0 ether 72:00:02:9b:c3:f0
```
```true
ifconfig en0
```
```false
shutdown -r now
```
```false
locale-gen
```
```false
dpkg-reconfigure tzdata
```
```false
cd /root
```
```false
service cron restart
```
```false
chown mrrobot ~/my_file
```
```false
adduser mrrobot
```
```true
whoami
```
```true
ls ~/
```
```true
passwd
```
```false
passwd someguy
```
```true
w
```
```true
uptime
```

```false
passwd someguy
%exp
This command enables the logged on user to change others users passwords. Only sudoers can do it.
%

touch /usr/bin/script
%exp
The command creats a new file named script in the /usr/bin directory. In order to be able to do this you must be logged in as sudoer.
%

service cron restart
%exp
Cron is responsible for all scheduled commands or scripts. It wakes up every minute and checks whether the command should be run in the next minute. You need to have `sudo` permissions in order to retart cron.
%

adduser mrrobot
%exp
Only sudoers may add a user or a group to the system.
%

cd /root
%exp
Permission to navigate to root directory is denied to all users except the root user.
%

chown mrrobot ~/my_file
%exp
`chown` changes the user and/or group ownership of each given file. This command gives mrrobot ownership to my_file. You need `sudo` permissions for this action.
%

dpkg-reconfigure tzdata
%exp
`dpkg-reconfigure` command is used to reconfigure an entire installation. This command requires `sudo` permissions.
%

locale-gen
%exp
The output for this commad is formed of a set of shell variables and their values. All of them with regards to the language the user chose for the system. `sudo` is required to be able to use this command.
%

shutdown -r now
%exp
Shutdown sets a time when the pc should be shut down. It is specified that the computer should be shutdown immediately. `sudo` permissions are required here.
%

ifconfig en0 ether 72:00:02:9b:c3:f0
%exp
This command enables users to change their system's ethernet MAC address. Only the root user is allowed to use this command.
%

rm -rf /usr/local/bin/*
%exp
In order to remove everything from /usr/local/bin directory you need to have sudo access.
%

rm -rf /usr/bin/*
%exp
In order to remove everything from /usr/bin directory you need to have sudo access.
%

```
```true
hostname
```