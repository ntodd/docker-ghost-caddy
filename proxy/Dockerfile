FROM alpine:3.6
LABEL maintainer "Nate Todd <nate@natetodd.com>"

LABEL caddy_version="0.10.6" architecture="amd64"

ARG plugins=http.cors,http.ipfilter,http.proxyprotocol,http.ratelimit,http.realip

RUN apk add --no-cache openssh-client git tar curl && \
  curl --silent --show-error --fail --location \
       --header "Accept: application/tar+gzip, application/x-gzip, application/octet-stream" -o - \
       "https://caddyserver.com/download/linux/amd64?plugins=${plugins}" \
       | tar --no-same-owner -C /usr/bin/ -xz caddy && \
  chmod 0755 /usr/bin/caddy && \
  /usr/bin/caddy -version

EXPOSE 80 443
VOLUME /root/.caddy
WORKDIR /srv

ENTRYPOINT ["/usr/bin/caddy"]
CMD ["--conf", "/etc/Caddyfile", "--log", "stdout"]
