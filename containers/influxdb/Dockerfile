FROM docker.io/influxdb:1.4-alpine

ADD influxdb.conf /etc/config/influxdb.conf

EXPOSE 2003
EXPOSE 8086

CMD [ "-config", "/etc/config/influxdb.conf" ]
