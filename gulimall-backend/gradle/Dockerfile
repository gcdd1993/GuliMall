# Second stage: minimal runtime environment
FROM adoptopenjdk/openjdk11-openj9:alpine-slim

ARG MODULE

ENV TZ=Asia/Shanghai

LABEL name=$MODULE

RUN set -ex \
    && sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update \
    && apk upgrade \
    && apk add --no-cache tzdata \
    && cp /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone

# copy arthas
COPY --from=hengyunabc/arthas:latest /opt/arthas /opt/arthas

WORKDIR /app

COPY $MODULE/build/docker/libs/*.jar /app/lib/
COPY $MODULE/build/docker/$MODULE /app/bin/run
COPY $MODULE/build/docker/$MODULE-*.jar /app/lib/

EXPOSE 8080

CMD ["/app/bin/run"]