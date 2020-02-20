FROM java:openjdk-8-jdk

ENV spark_ver 2.4.5

# Get Spark from US Apache mirror.
RUN mkdir -p /opt && \
    cd /opt && \
    curl https://archive.apache.org/dist/spark/spark-2.4.5/spark-2.4.5-bin-hadoop2.7.tgz | \
        tar -zx && \
    
    ln -s spark-${spark_ver}-bin-hadoop2.7 spark && \
    echo Spark ${spark_ver} installed in /opt
   


ADD /docker/start-common.sh /docker/start-worker.sh /docker//start-master.sh /
RUN chmod +x /start-common.sh /start-master.sh /start-worker.sh
ENV PATH $PATH:/opt/spark/bin

