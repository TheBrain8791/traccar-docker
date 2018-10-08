FROM openjdk:8-jre-alpine

ENV TRACCAR_VERSION 4.0-mod-01

WORKDIR /opt/traccar

RUN set -ex && \
    apk add --no-cache --no-progress wget && \
    wget -qO /tmp/traccar.zip https://github.com/TheBrain8791/traccar/releases/download/v$TRACCAR_VERSION/traccar-other-$TRACCAR_VERSION.zip && \
    unzip -qo /tmp/traccar.zip -d /opt/traccar && \
    rm /tmp/traccar.zip && \
    apk del wget

ENTRYPOINT ["java", "-Xms128m", "-Xmx128m", "-Djava.net.preferIPv4Stack=true"]

CMD ["-jar", "tracker-server.jar", "conf/traccar.xml"]
