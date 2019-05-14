# frp-deb-package
This is a pre-packaged Debian Package for (frp)[https://github.com/fatedier/frp] in order to save your time.

The package installs both frpc and frps at same time, frps and frpc binary file will be placed at /usr/bin, configuration files will be placed at /etc/frp. 

Systemd services are described at /etc/systemd/system. Both frpc and frps have 2 methods to use:

1. Directly use frps.service or frpc.services. This will load /etc/frp/frps.ini or /etc/frp/frpc.ini configuration file.
 
2. Use frps@ConfigFileNameWithoutIni.services or frpc@ConfigFileNameWithoutIni.services. This will load /etc/frp/ConfigFileName.ini instead. This is extremely useful when u want to run multiple frp clients.
