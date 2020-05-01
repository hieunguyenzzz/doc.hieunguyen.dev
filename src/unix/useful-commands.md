---
name: Useful Command
menu: Unix
route: unix/useful-command
---


# Userful command

## Find largest files

```shell script
find $HOME -type f -printf '%s %p\n' | sort -nr | head -10
```

## Check process run at port 

```shell script
sudo netstat -lntp | grep varnish
```