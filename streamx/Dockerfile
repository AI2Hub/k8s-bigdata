FROM openjdk:8-jdk-alpine

# 时区设置为上海时区
RUN sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories \
    && apk add tzdata curl bash docker && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone && apk del tzdata


ADD streamx-console-service-1.2.4 /opt/streamx-console-service-1.2.4
ADD flink-1.13.6 /opt/soft/flink-1.13.6
ADD kubectl /usr/local/bin/kubectl


RUN ln -s /opt/streamx-console-service-1.2.4 /opt/streamx && chmod +x /usr/local/bin/kubectl

ENV DB_HOST='' \
    DB_PORT=3306 \
    DB_NAME='streamx'\
    DB_USER='streamx' \
    DB_PASSWD='streamx'


EXPOSE 10000

WORKDIR /opt/streamx


ENTRYPOINT ["/bin/bash","-c","/opt/streamx/bin/startup.sh"]