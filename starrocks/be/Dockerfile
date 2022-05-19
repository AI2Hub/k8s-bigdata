FROM 10.150.30.17:28080/ops/centos7-jdk8

#时区设置
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo Asia/Shanghai > /etc/timezone

ADD be /starrocks/be

EXPOSE 9060 8040 9050 8060

VOLUME ["/starrocks/be/storage", "/starrocks/be/log"]

ENTRYPOINT ["sh", "/starrocks/be/bin/start_be.sh"]