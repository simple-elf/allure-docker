FROM openjdk:8-jre-alpine

ARG RELEASE=1.13.0
RUN echo $RELEASE
ARG ALLURE_REPO=https://dl.bintray.com/qameta/generic/allurectl

RUN apk update
RUN apk add bash
RUN apk add wget
RUN apk add unzip

RUN mkdir -p /allurectl-$RELEASE/bin/
RUN wget $ALLURE_REPO/$RELEASE/allurectl_linux_386 -O /allure-$RELEASE/bin/allurectl --no-verbose

RUN rm -rf /var/cache/apk/*

RUN chmod -R +x /allurectl-$RELEASE/bin

ENV ROOT=/app
ENV PATH=$PATH:/allurectl-$RELEASE/bin

RUN mkdir -p $ROOT

WORKDIR $ROOT
#COPY entrypoint.sh /entrypoint.sh

#ENTRYPOINT ["/entrypoint.sh"]
#ENTRYPOINT ["allure --version"]