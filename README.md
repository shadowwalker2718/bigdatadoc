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



## Data:

https://snap.stanford.edu/data/web-Google.html

https://www.safaribooksonline.com/library/view/scalable-programming-with/9781788997881/video6_3.html

https://github.com/apache/incubator-toree

```
ansible u3 -a "pip install https://dist.apache.org/repos/dist/dev/incubator/toree/0.2.0/snapshots/dev1/toree-pip/toree-0.2.0.dev1.tar.gz"
ansible u3 -a "jupyter toree install"
```

Upgrade system:
```
pip install --upgrade --force-reinstall --no-cache-dir jupyter
pip install --upgrade --force-reinstall --no-cache-dir ipython

apt-get update && apt-get upgrade -y
```


## start jupyter

in `u3`:

```
cd /opt/share/notebook
jupyter notebook  --allow-root
```

Change bind address and port:  
```
$jupyter notebook --generate-config
Writing default config to: /root/.jupyter/jupyter_notebook_config.py
```


