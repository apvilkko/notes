# Using VirtualBox for testing old Internet Explorer versions

To forward a localhost port (assumed 9000 here), configure in the slave OS (inside VirtualBox):
```
netsh interface portproxy add v4tov4 listenport=9000 connectport=9000 connectaddress=10.0.2.2
```
