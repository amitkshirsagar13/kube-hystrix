FROM frolvlad/alpine-oraclejdk8:slim
VOLUME /tmp
ADD hystrix-turbine-0.1.0.jar app.jar
RUN apk add --update curl && \
    rm -rf /var/cache/apk/*
ADD configcheck.sh configcheck.sh
RUN sh -c 'touch /app.jar'
EXPOSE 1234
ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "/configcheck.sh && java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]