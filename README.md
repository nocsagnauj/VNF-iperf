# VNF\_iperf

This project creates iperf dockers to simulate VNFs in hosts.
There is a Dockerfile for the server and the client.

The configuration parameters can be modified via environnement variables
and so, the user can get the server IP address thanks to "docker inspect"
and pass it to the client via the IPERF\_SRV\_IP environnement variable.


## Server

This Dockerfile launches an iperf server listening to port 9435
and reports at intervals of 1 second

These values can be changed via the environnement values:
- IPERF\_SRV\_PORT 9435
- IPERF_INTERVAL 1

The docker is built as follows:

\# docker build -t vnf\_iperf\_srv ./server/

The docker should be called as follows:

\# docker run -ti --rm -P \[-e "IPERF\_SRV\_PORT=9435"\] --name vnf\_iperf\_srv vnf\_iperf\_srv:latest

## Client

This Dockerfile launches an iperf client 
sending 100Kbps traffic 
to a server at ip '172.17.0.2' 
who is listening to port: 9435
and prints reports at intervals of 1 second

These values can be changed via the environnement values:

- IPERF\_SRV\_IP 172.17.0.2
- IPERF\_SRV\_PORT 9435
- IPERF\_INTERVAL 1
- IPERF\_BW 100K

The docker is built as follows:

\#docker build -t vnf\_iperf\_client ./client/

The docker should be called as follows:

\# docker run -ti --rm -P \[-e "IPERF\_SRV\_PORT=9435"\] --name vnf\_iperf\_client vnf\_iperf\_client:latest
