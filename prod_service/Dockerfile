FROM alpine:3.12
RUN apk add --no-cache openjdk8-jre-base \
    && rm -rf /tmp/* /var/cache/apk/
EXPOSE 8080
CMD ["/opt/tomcat/bin/catalina.sh", "run"]