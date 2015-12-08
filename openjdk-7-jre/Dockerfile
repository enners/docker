FROM alpine:3.2
MAINTAINER kenners <knutenners+git@gmail.com>

LABEL arch=x86_64 \
    java.version="1.7.0_79" \
    java.vendor=OpenJDK \
    java.jvm=JRE \
    os=alpine

RUN set -ex \
    && packages='openjdk7-jre-base' \
    && apk add --update ${packages} \
    \
    && rm -rf /var/cache/apk/*

CMD ["/usr/bin/java", "-version"]

