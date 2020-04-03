# docker buildx build --platform linux/arm64 -t azking/arm64_zfile:2.2   .  --push
#arm64v8/openjdk
#FROM ubuntu
FROM arm64v8/openjdk:8
MAINTAINER azking <12345665@qq.com>
ENV VERSION 2.2

WORKDIR /root

RUN apt update \
    && apt install -y wget openjdk-8-jre-headless unzip \
    && wget https://github.com/itwarlock/zfile/release/zfile-${VERSION}.war \
    && mkdir zfile && unzip zfile-${VERSION}.war -d zfile && rm -rf zfile-${VERSION}.war \
    && chmod +x ~/zfile/bin/*.sh \
    && apt -y remove wget unzip \
    && apt clean \
    && apt autoclean
EXPOSE 8080

CMD ./zfile/bin/start.sh && tail -f /dev/null