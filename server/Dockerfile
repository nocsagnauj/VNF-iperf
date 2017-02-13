#Author Juan GASCON
#This Dockerfile launches an iperf server listening to
#PORT: 9435
#and reports at intervals of 1 second

FROM alpine:latest
LABEL MAINTAINER "Juan GASCON <nocsagnauj@gmail.com>"

RUN apk update && apk add iperf

ENV IPERF_SRV_PORT 9435
ENV IPERF_INTERVAL 1

EXPOSE $IPERF_SRV_PORT

CMD iperf -s -p $IPERF_SRV_PORT -i $IPERF_INTERVAL