# frp-deb-package
This is a pre-packaged Debian Package for (frp)[https://github.com/fatedier/frp] in order to save your time.

The package installs both frpc and frps at same time, frps and frpc binary file will be placed at /usr/bin, configuration files will be placed at /etc/frp. 

Systemd services are described at /etc/systemd/system. Both frpc and frps have 2 methods to use:

1. Directly use frps.service or frpc.service. This will load /etc/frp/frps.ini or /etc/frp/frpc.ini configuration file.
 
2. Use frps@ConfigFileNameWithoutIni.service or frpc@ConfigFileNameWithoutIni.service. This will load /etc/frp/ConfigFileName.ini instead. This is extremely useful when u want to run multiple frp clients.

Example:
```
$ systemctl start/stop/restart/enable/disable frps
$ systemctl start/stop/restart/enable/disable frpc
```
directly run frps loading /etc/frp/frps.ini 
or run frpc loading /etc/frp/frpc.ini

```
$ systemctl start/stop/restart/enable/disable frps@test
```
run frps loading /etc/frp/test.ini. 

```
$ systemctl start/stop/restart/enable/disable frpc@test
```
run frpc loading /etc/frp/test.ini. 

**DON'T RUN FRPS AND FRPC WITH SAME NAME OF CONFIGUARION FILE**
