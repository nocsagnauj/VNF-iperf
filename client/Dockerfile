#Author Juan GASCON
#This Dockerfile launches an iperf client
#sending 100Kbps traffic to a server at
#IP: 172.17.0.2
#listening to PORT: 9435
#and reports at intervals of 1 second

FROM alpine:latest
LABEL MAINTAINER "Juan GASCON <nocsagnauj@gmail.com>"

RUN apk update && apk add iperf

ENV IPERF_SRV_IP 172.17.0.2
ENV IPERF_SRV_PORT 9435
ENV IPERF_INTERVAL 1
ENV IPERF_BW 100K

EXPOSE $IPERF_SRV_PORT

CMD iperf -c $IPERF_SRV_IP -p $IPERF_SRV_PORT -b $IPERF_BW -i $IPERF_INTERVAL