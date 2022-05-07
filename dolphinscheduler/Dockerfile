FROM apache/dolphinscheduler:2.0.5

RUN sed -i "s@http://deb.debian.org@http://mirrors.aliyun.com@g" /etc/apt/sources.list &&\
    apt-get update && \
    apt-get install -y --no-install-recommends python3-pip && \
    rm -rf /var/lib/apt/lists/*

COPY ./apache-dolphinscheduler-2.0.5-bin/lib /opt/dolphinscheduler/lib
COPY ./apache-dolphinscheduler-2.0.5-bin/ui /opt/dolphinscheduler/ui
COPY mysql-connector-java-8.0.28.jar /opt/dolphinscheduler/lib
COPY datax /opt/soft/datax
COPY flink-1.14.4 /opt/soft/flink-1.14.4 
COPY spark-3.2.1-bin-hadoop3.2 /opt/soft/spark-3.2.1-bin-hadoop3.2

RUN ln -s /opt/soft/spark-3.2.1-bin-hadoop3.2 /opt/soft/spark2 && \
    ln -s /opt/soft/flink-1.14.4 /opt/soft/flink