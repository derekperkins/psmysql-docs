# Percona Server for MySQL 8.0.23-14 (2021-05-12)

* **Installation** [Installing Percona Server for MySQL](https://www.percona.com/doc/percona-server/8.0/installation.html)


[Percona Server for MySQL](https://www.percona.com/software/mysql-database/percona-server) 8.0.23-14
includes all the features and bug fixes available in
[MySQL 8.0.23 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-23.html)
in addition to enterprise-grade features developed by Percona.

## New Features


* [PS-7364](https://jira.percona.com/browse/PS-7364): The net_buffer_length status variable shows the buffer size of the current connection. Specify SHOW GLOBAL to see cumulative buffer size for all connections. For more information, see Adaptive Network Buffers.


* [PS-5364](https://jira.percona.com/browse/PS-5364): Update the keyring_vault plugin to support KV Secrets Engine Version 2 (kv-v2) (Thanks to Andrey Prokofyev for reporting this issue)


* [PS-4894](https://jira.percona.com/browse/PS-4894): Users can add calculated/virtual columns + index for the MyRocks storage engine.


* [PS-7125](https://jira.percona.com/browse/PS-7125): Users can reconfigure the TLS certificate at runtime and reload the certificate to the X Plugin (Upstream [#99895](http://bugs.mysql.com/bug.php?id=99895))


* [PS-7442](https://jira.percona.com/browse/PS-7442): Add documentation for the MyRocks Information Schema Tables ROCKSDB_ACTIVE_COMPACTION_STATS and ROCKSDB_COMPACTION_HISTORY.


* [PS-7441](https://jira.percona.com/browse/PS-7441): Add documentation for the RocksDB variable rocksdb_max_compaction_history and deprecated the strict_collation_check variable.


* [PS-7049](https://jira.percona.com/browse/PS-7049): Update the SELinux profile and the AppArmor Policy, making these security features easier to implement for organizations.

## Improvements


* [PS-5846](https://jira.percona.com/browse/PS-5846): Add support for the [default value clause](https://dev.mysql.com/doc/refman/8.0/en/data-type-defaults.html) for the MyRocks storage engine. (Thanks to user denji for reporting this issue)


* [PS-6780](https://jira.percona.com/browse/PS-6780): Optimize support for collations other than latin1/utf8 in MyRocks. This support allows MyRocks to reconstruct and return data directly from an index read.

## Bugs Fixed


* [PS-1956](https://jira.percona.com/browse/PS-1956): Update specific data types to 64-bit to make slow query logs more efficient.


* [PS-7593](https://jira.percona.com/browse/PS-7593): If a transaction has executed, changing the tx-isolation level in a session is not honored and may cause service failure.


* [PS-7578](https://jira.percona.com/browse/PS-7578): Fix the replication failure on Update when a replica server has a primary key and the source server does not.


* [PS-7498](https://jira.percona.com/browse/PS-7498): Prevent the replication coordinator thread from being stuck due to the MASTER_DELAY while handling the partial relay log transactions. (Upstream [#102647](http://bugs.mysql.com/bug.php?id=102647))


* [PS-7474](https://jira.percona.com/browse/PS-7474): ROCKSDB: Row not retrieved when using character sets that do not support Secondary Key index-only scans.


* [PS-7618](https://jira.percona.com/browse/PS-7618): Added the libmysqlclient.so.21(libmysqlclient_21)(64bit) to the PS80 Repository(Thanks to user Mark Frost for reporting this issue).


* [PS-7098](https://jira.percona.com/browse/PS-7098): MyRocks: ICP fails with character sets that do not support Secondary Key index-only scans, for example, utf8mb4. (Thanks to user denis for reporting this issue)


* [PS-4497](https://jira.percona.com/browse/PS-4497): Incorrect option error message for mysqlbinlog.


* [PS-7617](https://jira.percona.com/browse/PS-7617): In the Grant tables, the Timestamp column displays when the last change occurred to a user. In specific tables, the Timestamp column may be set to NULL.


* [PS-7566](https://jira.percona.com/browse/PS-7566): Correct version matching in RPM spec changelog for PS packages


* [PS-7499](https://jira.percona.com/browse/PS-7499): Improve the error log when MyRocks fails with rocksdb_validate_tables=1


* [PS-7495](https://jira.percona.com/browse/PS-7495): Block Tablespace DDL with LOCK TABLES FOR BACKUP (Upstream [#102175](http://bugs.mysql.com/bug.php?id=102175))


* [PS-7291](https://jira.percona.com/browse/PS-7291): Run a variable value check when setting it with ‘set persist_only’


* [PS-7492](https://jira.percona.com/browse/PS-7492): Update slow log formatting for tmp tables related stats

## Known Issues


* [PS-7683](https://jira.percona.com/browse/PS-7683): If you are upgrading MyRocks from 8.0.22 to 8.0.23, you must run the following commands to add the ROCKSDB_COMPACTION_HISTORY and ROCKSDB_COMPACTION_STATS tables:

> ```
> INSTALL PLUGIN ROCKSDB_COMPACTION_HISTORY SONAME 'ha_rocksdb.so';
> INSTALL PLUGIN ROCKSDB_COMPACTION_STATS SONAME 'ha_rocksdb.so';
> ```
