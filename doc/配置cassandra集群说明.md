

# 1.安装和配置java

```
wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie"  http://download.oracle.com/otn-pub/java/jdk/8u91-b14/jre-8u91-linux-x64.tar.gz
tar -xzf jre-8u91-linux-x64.tar.gz
mv jre1.8.0_91 /usr/lib/jre180
```

```
vi ~/.bashrc
```
加入三行，内容如下：
```
JAVA_HOME=/usr/lib/jre180
JAVA_BIN=/usr/lib/jre180/bin
export JAVA_HOME JAVA_BIN
```
```
source ~/.bashrc
```

# 2.下载和配置cassandra

```
cd /alidata1/cassandra
wget http://apache.fayea.com/cassandra/3.7/apache-cassandra-3.7-bin.tar.gz
tar -xzf apache-cassandra-3.7-bin.tar.gz
mv apache-cassandra-3.7 cassandra
```

打开配置
```
cd cassandra
vi ./conf/cassandra.yaml
```

配置改为：
```
cluster_name: 'dc1'
num_tokens: 256
seed_provider:
  - class_name: org.apache.cassandra.locator.SimpleSeedProvider
    parameters:
         - seeds: "yf.jfgou.com"
listen_address: 服务器的ip地址
rpc_address: 服务器的ip地址
endpoint_snitch: GossipingPropertyFileSnitch
data_file_directories:
     - /alidata1/cqldata/cassandra/data
commitlog_directory: /alidata1/cqldata/cassandra/commitlog
saved_caches_directory: /alidata1/cqldata/cassandra/saved_caches
```

创建数据文件夹：
```
mkdir /alidata1/cqldata
mkdir /alidata1/cqldata/cassandra
```

新增节点仍然按照上面的配置即可



# 3.使用supervisor

```
vi /etc/supervisor/conf.d/cassandra.conf
```

```
[program:cassandra]
command=/alidata1/cassandra/cassandra/bin/cassandra -R -f
environment=JAVA_HOME=/usr/lib/jre180,JAVA_BIN=/usr/lib/jre180/bin
autostart=true
autorestart=true
startretries=1

stdout_logfile=/tmp/cassandra.log
stdout_logfile_maxbytes=10MB
stdout_logfile_backups=10

stderr_logfile = /tmp/cassandra.err
stderr_logfile_maxbytes=10MB
stderr_logfile_backups=10
```

启动cassandra
```
supervisorctl update
supervisorctl start cassandra
```


# 4. 检查

## 看看有什么错误
```
cat /tmp/cassandra.log
cat /tmp/cassandra.err 
cat /var/log/supervisor/supervisord.log
```

## 看看node情况
```
root@BENCH-HOST:/alidata1/cassandra/cassandra# ./bin/nodetool status
Datacenter: dc1
===============
Status=Up/Down
|/ State=Normal/Leaving/Joining/Moving
--  Address          Load       Tokens       Owns (effective)  Host ID                               Rack
UN  218.244.145.220  160.4 KiB  256          100.0%            519c6a0d-0743-4d7c-b19c-aec5808cd758  rack1
```

## 当集群有两台机器的时候：
```
root@BENCH-HOST:/alidata1/cassandra/cassandra# ./bin/nodetool status
Datacenter: dc1
===============
Status=Up/Down
|/ State=Normal/Leaving/Joining/Moving
--  Address          Load       Tokens       Owns (effective)  Host ID                               Rack
UN  121.40.58.78     276.89 KiB  256          48.0%             2580464d-6617-4330-948d-1d67daa7f6a2  rack1
UN  218.244.145.220  225.71 KiB  256          52.0%             519c6a0d-0743-4d7c-b19c-aec5808cd758  rack1
```

# 5.添加密码

打开cassandra.yaml

改为：
```
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
```

修改密码：
```
root@YF-HOST:/alidata1/cassandra/cassandra# ./bin/cqlsh 121.40.58.78 -u cassandra -p cassandra
Connected to dc1 at 121.40.58.78:9042.
[cqlsh 5.0.1 | Cassandra 3.7 | CQL spec 3.4.2 | Native protocol v4]
Use HELP for help.
cassandra@cqlsh> alter user cassandra with password 'cylancas';
```




