FROM 10.150.30.17:28080/ops/centos7-jdk8

ADD fe /starrocks/fe

ENV JVM_OPTS='-Xmx1024m'


EXPOSE 8030 9020 9030 9010

VOLUME ["/starrocks/fe/meta","/starrocks/fe/log"]

ENTRYPOINT ["sh", "/starrocks/fe/bin/start_fe.sh"]