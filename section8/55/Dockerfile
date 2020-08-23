FROM alpine:3.9

COPY docker-entrypoint.sh /usr/local/bin

RUN \
adduser -g mongodb -DH -u 1000 mongodb; \
apk --no-cache add mongodb=4.0.5-r0; \
chmod +x /usr/local/bin/docker-entrypoint.sh; \
mkdir -p /data/db; \
chown -R mongodb:mongodb /data/db;

VOLUME /data/db 

EXPOSE 27107

ENTRYPOINT [ "docker-entrypoint.sh" ]
CMD [ "mongod" ]

# < docker exec -it  sharp_lederberg sh
# / # mongo
# MongoDB shell version v4.0.5
# connecting to: mongodb://127.0.0.1:27017/?gssapiServiceName=mongodb
