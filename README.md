# synclpw

Simple shell script to synchronize a local account password across multiple systems

## Requirements

*  POSIX shell (bash, dash, zsh, ksh, etc)
*  ssh 

## Usage

### Setup

1. enable root ssh logins on all hosts to be synchronized
2. configure ssh keys (or some other passwordless auth) for the root account (if you cannot ssh to the hosts as root without providing a password, this script will not work)
3. create a text file with name `hosts` listing the hosts you wish to sync and save it in the same directory as `synclpw`

```
# example hosts file

server1
server2.example.net
192.168.1.10
```

### Synchronizing

1. set the new local account password normally, i.e., `passwd <username>`
2. run the script, `./synclpw <username>`