FROM abiosoft/caddy-docker:latest
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
          }
          ]"
