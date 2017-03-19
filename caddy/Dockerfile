FROM abiosoft/caddy:latest
LABEL org.freenas.interactive="false"                                         \
      org.freenas.version="1"                                                 \
      org.freenas.upgradeable="false"                                         \
      org.freenas.expose-ports-at-host="true"                                 \
      org.freenas.autostart="true"                                            \
      org.freenas.port-mappings="80:80/tcp,443:443/tcp,2015:2015/tcp"                    \
      org.freenas.volumes="[						                  \
          {								                        \
              \"name\": \"/etc/Caddyfile\",					      \
              \"descr\": \"Caddy configuration\"		                              \
          },                                                                  \
          {								                        \
              \"name\": \"/root/.caddy\",				\
              \"descr\": \"Caddy datastore\"		                              \
          },                                                                  \
          {								                        \
              \"name\": \"/var/www/html\",				\
              \"descr\": \"Default public html directory\"		\
          }                                                                   \
          ]"
