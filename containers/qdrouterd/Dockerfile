FROM docker.io/enmasseproject/qdrouterd-base:1.2.0

RUN \
  curl -sL https://raw.githubusercontent.com/eclipse/hono/master/demo-certs/certs/qdrouter-key.pem --output /etc/qpid-dispatch/qdrouter-key.pem && \
  curl -sL https://raw.githubusercontent.com/eclipse/hono/master/demo-certs/certs/qdrouter-cert.pem --output /etc/qpid-dispatch/qdrouter-cert.pem && \
  curl -sL https://raw.githubusercontent.com/eclipse/hono/master/demo-certs/certs/trusted-certs.pem --output /etc/qpid-dispatch/trusted-certs.pem

ADD qdrouterd.conf /etc/qpid-dispatch/qdrouterd.conf

RUN \
  mkdir -p /var/lib/qdrouterd && \
  echo "http-secret" | saslpasswd2 -p -f /var/lib/qdrouterd/qdrouterd.sasldb -c http-adapter -a HONO && \
  echo "mqtt-secret" | saslpasswd2 -p -f /var/lib/qdrouterd/qdrouterd.sasldb -c mqtt-adapter -a HONO && \
  echo "secret" | saslpasswd2 -p -f /var/lib/qdrouterd/qdrouterd.sasldb -c hono-client -a HONO && \
  echo "verysecret" | saslpasswd2 -p -f /var/lib/qdrouterd/qdrouterd.sasldb -c consumer -a HONO && \
  \ 
  sasldblistusers2 -f /var/lib/qdrouterd/qdrouterd.sasldb
