# bigdatadoc

http://u3:50070/dfshealth.html#tab-overview  
http://u3:8088/cluster

hue in u3:

https://github.com/cloudera/hue  
http://blog.csdn.net/wenlong237/article/details/19735603

hive set up:

https://cwiki.apache.org/confluence/display/Hive/Setting+Up+HiveServer2

hadoop cluster:

https://linode.com/docs/databases/hadoop/how-to-install-and-set-up-hadoop-cluster/

spark with yarn:

https://linode.com/docs/databases/hadoop/install-configure-run-spark-on-top-of-hadoop-yarn-cluster/

kafka +  zookeeper:

https://www.youtube.com/watch?v=SxHsnNYxcww  
https://engineering.linkedin.com/blog/2016/05/open-sourcing-kafka-monitor

https://www.safaribooksonline.com/library/view/learning-path-kafka/9781491988961/video301662.html

```
ansible redis -a "/opt/share/redis/redis_start.sh"
ansible redis -a "/opt/share/redis/redis_shutdown.sh"
```


`ssh u3` and then `$HIVE_HOME/bin/hive --service hiveserver2`



```
ansible hadoop_master -a "start-dfs.sh"
ansible hadoop_master -a "start-yarn.sh"
ansible hadoop_master -a "stop-yarn.sh"
ansible hadoop_master -a "stop-dfs.sh"


ansible hadoop -a "jps"
```


kafka:

1. start zookeeper

ansible kafka -a "zookeeper-server-start.sh $KAFKA_HOME/config/zookeeper.properties &"

or run it in each machine of u0, u1 and u3

2. start kafka

ssh u0: kafka-server-start.sh /opt/share/kafka/config/server.u0.properties
ssh u1: kafka-server-start.sh /opt/share/kafka/config/server.u1.properties
ssh u2: kafka-server-start.sh /opt/share/kafka/config/server.u2.properties


