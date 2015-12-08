FROM kenners/java:7
MAINTAINER ennersk

ENV GITBUCKET_VERSION=3.9 \
    RELEASE_URL=https://github.com/gitbucket/gitbucket/releases/download

WORKDIR /opt/gitbucket
VOLUME	/git

RUN apk add --update curl \
    \
    && mkdir -p /opt/gitbucket \
    && curl -L ${RELEASE_URL}/${GITBUCKET_VERSION}/gitbucket.war \
    > /opt/gitbucket/gitbucket.war \
    && chown -R nobody:nogroup /opt/gitbucket \
    && chown -R nobody:nogroup /git \
    \
    && apk del curl && rm -rf /var/cache/apk/*

# ssh, web ui
EXPOSE 2222 8080
USER nobody
ENTRYPOINT ["java", "-jar", "gitbucket.war"]
CMD ["--gitbucket.home=/git"]

