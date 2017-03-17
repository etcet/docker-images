FROM alpine:3.5

LABEL caddy_version="0.9.5" architecture="amd64"

ARG plugins=git

RUN apk add --no-cache openssh-client git tar curl

RUN curl --silent --show-error --fail --location \
      --header "Accept: application/tar+gzip, application/x-gzip, application/octet-stream" -o - \
      "https://caddyserver.com/download/build?os=linux&arch=amd64&features=${plugins}" \
    | tar --no-same-owner -C /usr/bin/ -xz caddy \
 && chmod 0755 /usr/bin/caddy \
 && /usr/bin/caddy -version \
 && setcap cap_net_bind_service=+ep /usr/bin/caddy

EXPOSE 80 443 2015
RUN useradd -ms /bin/bash caddy
USER caddy
VOLUME /home/caddy/.caddy
WORKDIR /srv
COPY Caddyfile /etc/Caddyfile
COPY index.html /srv/index.html

ENTRYPOINT ["/usr/bin/caddy"]
CMD ["--conf", "/etc/Caddyfile", "--log", "stdout"]

LABEL org.freenas.interactive="false"                                         \
      org.freenas.version="1"                                                 \
      org.freenas.upgradeable="false"                                         \
      org.freenas.expose-ports-at-host="true"                                 \
      org.freenas.autostart="true"                                            \
      org.freenas.port-mappings="80:80/tcp,443:443/tcp,2015:2015/tcp"                    \
      org.freenas.volumes="[						                  \
          {								                        \
              \"name\": \"/srv\",					      \
              \"descr\": \"HTML content\"		                              \
          },                                                                  \
          {								                        \
              \"name\": \"/etc/Caddyfile\",				\
              \"descr\": \"Caddy config\"		                              \
          }"
