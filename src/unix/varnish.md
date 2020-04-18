---
name: Varnish
menu: Unix
route: unix/varnish
---

# Varnish 
## Configuration
https://varnish-cache.org/docs/trunk/installation/install_debian.html

### List all UUIDs

## Configuration

### change nginx port from 80 to 8080

```shell script
sudo netstat -lntp | grep nginx
```

find all the host file of nginx and change the listen port


### Make Varnish systemd Port 80

The way systemd works we have to create a drop-in systemd file that overrides the ExecStart line. This ensures that the changes made directly to the systemd service are not overwritten when there is an upgrade.

```shell script
sudo mkdir -p /etc/systemd/system/varnish.service.d
sudo nano /etc/systemd/system/varnish.service.d/local.conf
```

run `service varnish status` and grab the bellow stuff 

```shell script
/usr/sbin/varnishd -j unix,user=vcache -F -a :6081 -T localhost:6082 -f /etc/varnish/default.vcl -S /etc/varnish/secret -s malloc,256m
```

put it into `/etc/systemd/system/varnish.service.d/local.conf` with the port changed to 80

```shell script
/usr/sbin/varnishd -j unix,user=vcache -F -a :80 -T localhost:6082 -f /etc/varnish/default.vcl -S /etc/varnish/secret -s malloc,256m
```

reload the varnish

```shell script
 systemctl daemon-reload
```

```shell script
service varnish restart
```

## Flush varnish 

i.e flush this page https://www.mobelaris.com/sv/

```shell script
varnishadm -T localhost:6082 -S /etc/varnish/secret ban "req.http.host == www.mobelaris.com && req.url == /sv/"
```