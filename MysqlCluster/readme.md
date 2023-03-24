# 容器启动查询
## init-mysql
```
[root@master ~]# kubectl logs mysql-0 init-mysql
+ [[ mysql-0 =~ -([0-9]+)$ ]]
+ ordinal=0
+ echo '[mysqld]'
+ echo server-id=100
+ [[ 0 -eq 0 ]]
+ cp /mnt/config-map/primary.cnf /mnt/conf.d/
```

## mysql
```
[root@master ~]# kubectl logs mysql-0 init-mysql
+ [[ mysql-0 =~ -([0-9]+)$ ]]
+ ordinal=0
+ echo '[mysqld]'
+ echo server-id=100
+ [[ 0 -eq 0 ]]
+ cp /mnt/config-map/primary.cnf /mnt/conf.d/
[root@master ~]#  kubectl logs mysql-0 mysql
2023-03-24 07:09:15+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 5.7.36-1debian10 started.
2023-03-24 07:09:15+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
2023-03-24 07:09:15+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 5.7.36-1debian10 started.
2023-03-24T07:09:15.578039Z 0 [Warning] TIMESTAMP with implicit DEFAULT value is deprecated. Please use --explicit_defaults_for_timestamp server option (see documentation for more details).
2023-03-24T07:09:15.579656Z 0 [Note] mysqld (mysqld 5.7.36-log) starting as process 1 ...
2023-03-24T07:09:15.580982Z 0 [Warning] No argument was provided to --log-bin, and --log-bin-index was not used; so replication may break when this MySQL server acts as a master and has his hostname changed!! Please use '--log-bin=mysql-0-bin' to avoid this problem.
2023-03-24T07:09:15.607203Z 0 [Note] InnoDB: PUNCH HOLE support available
2023-03-24T07:09:15.607219Z 0 [Note] InnoDB: Mutexes and rw_locks use GCC atomic builtins
2023-03-24T07:09:15.607222Z 0 [Note] InnoDB: Uses event mutexes
2023-03-24T07:09:15.607224Z 0 [Note] InnoDB: GCC builtin __atomic_thread_fence() is used for memory barrier
2023-03-24T07:09:15.607226Z 0 [Note] InnoDB: Compressed tables use zlib 1.2.11
2023-03-24T07:09:15.607229Z 0 [Note] InnoDB: Using Linux native AIO
2023-03-24T07:09:15.607506Z 0 [Note] InnoDB: Number of pools: 1
2023-03-24T07:09:15.607671Z 0 [Note] InnoDB: Using CPU crc32 instructions
2023-03-24T07:09:15.609449Z 0 [Note] InnoDB: Initializing buffer pool, total size = 128M, instances = 1, chunk size = 128M
2023-03-24T07:09:15.617162Z 0 [Note] InnoDB: Completed initialization of buffer pool
2023-03-24T07:09:15.620370Z 0 [Note] InnoDB: If the mysqld execution user is authorized, page cleaner thread priority can be changed. See the man page of setpriority().
2023-03-24T07:09:15.644357Z 0 [Note] InnoDB: Highest supported file format is Barracuda.
2023-03-24T07:09:16.057153Z 0 [Note] InnoDB: Creating shared tablespace for temporary tables
2023-03-24T07:09:16.057222Z 0 [Note] InnoDB: Setting file './ibtmp1' size to 12 MB. Physically writing the file full; Please wait ...
2023-03-24T07:09:19.387580Z 0 [Note] InnoDB: File './ibtmp1' size is now 12 MB.
2023-03-24T07:09:19.388076Z 0 [Note] InnoDB: 96 redo rollback segment(s) found. 96 redo rollback segment(s) are active.
2023-03-24T07:09:19.388095Z 0 [Note] InnoDB: 32 non-redo rollback segment(s) are active.
2023-03-24T07:09:19.388889Z 0 [Note] InnoDB: Waiting for purge to start
2023-03-24T07:09:19.446231Z 0 [Note] InnoDB: 5.7.36 started; log sequence number 12666149
2023-03-24T07:09:19.447072Z 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
2023-03-24T07:09:19.447166Z 0 [Note] Plugin 'FEDERATED' is disabled.
2023-03-24T07:09:19.694456Z 0 [Note] InnoDB: Buffer pool(s) load completed at 230324  7:09:19
2023-03-24T07:09:19.787835Z 0 [Note] Found ca.pem, server-cert.pem and server-key.pem in data directory. Trying to enable SSL support using them.
2023-03-24T07:09:19.787892Z 0 [Note] Skipping generation of SSL certificates as certificate files are present in data directory.
2023-03-24T07:09:19.787897Z 0 [Warning] A deprecated TLS version TLSv1 is enabled. Please use TLSv1.2 or higher.
2023-03-24T07:09:19.787898Z 0 [Warning] A deprecated TLS version TLSv1.1 is enabled. Please use TLSv1.2 or higher.
2023-03-24T07:09:19.790876Z 0 [Warning] CA certificate ca.pem is self signed.
2023-03-24T07:09:19.790926Z 0 [Note] Skipping generation of RSA key pair as key files are present in data directory.
2023-03-24T07:09:19.794145Z 0 [Note] Server hostname (bind-address): '*'; port: 3306
2023-03-24T07:09:19.794362Z 0 [Note] IPv6 is available.
2023-03-24T07:09:19.794440Z 0 [Note]   - '::' resolves to '::';
2023-03-24T07:09:19.794469Z 0 [Note] Server socket created on IP: '::'.
2023-03-24T07:09:19.795754Z 0 [Warning] Insecure configuration for --pid-file: Location '/var/run/mysqld' in the path is accessible to all OS users. Consider choosing a different directory.
2023-03-24T07:09:20.029315Z 0 [Note] Failed to start slave threads for channel ''
2023-03-24T07:09:20.567496Z 0 [Note] Event Scheduler: Loaded 0 events
2023-03-24T07:09:20.568119Z 0 [Note] mysqld: ready for connections.
Version: '5.7.36-log'  socket: '/var/run/mysqld/mysqld.sock'  port: 3306  MySQL Community Server (GPL)
2023-03-24T07:09:46.837520Z 9 [Warning] IP address '10.244.4.62' could not be resolved: Name or service not known
2023-03-24T07:09:46.844496Z 9 [Note] Start binlog_dump to master_thread_id(9) slave_server(101), pos(mysql-0-bin.000006, 756)
2023-03-24T07:10:40.115743Z 43 [Warning] IP address '10.244.3.116' could not be resolved: Name or service not known
2023-03-24T07:10:40.173087Z 43 [Note] Start binlog_dump to master_thread_id(43) slave_server(102), pos(mysql-0-bin.000006, 756)
```
## xtrabackup
```
[root@master ~]# kubectl logs mysql-0 xtrabackup
+ cd /var/lib/mysql
+ [[ -f xtrabackup_slave_info ]]
+ [[ -f xtrabackup_binlog_info ]]
+ [[ -f change_master_to.sql.in ]]
+ exec ncat --listen --keep-open --send-only --max-conns=1 3307 -c 'xtrabackup --backup --slave-info --stream=xbstream --host=127.0.0.1 --user=root'
```

# 案例验证
## POD 查询
```
[root@master ~]# kubectl get pod -l app=mysql
NAME      READY   STATUS    RESTARTS   AGE
mysql-0   2/2     Running   0          4m5s
mysql-1   2/2     Running   0          3m10s
mysql-2   2/2     Running   0          2m45s
```
## 表创建
```
kubectl run mysql-client --image=mysql:5.7 -i --rm --restart=Never --\
  mysql -h mysql-0.mysql -uroot -e'
CREATE DATABASE test;
CREATE TABLE test.messages (message VARCHAR(250));
INSERT INTO test.messages VALUES ('hello');
'
```

## 表查询
```
kubectl run mysql-client --image=mysql:5.7 -i --rm --restart=Never -- mysql -h mysql-0.mysql -uroot -e'SELECT * FROM test.messages'
```




# 参考资料
- [k8s运行mysql主从架构](https://www.cnblogs.com/wangguishe/p/17027398.html)
- [服务（Service）](https://kubernetes.io/zh-cn/docs/concepts/services-networking/service/)