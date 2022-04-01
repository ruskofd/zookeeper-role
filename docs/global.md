### Global options

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `zookeeper_ticktime`              | `2000`                       | The length of a single tick, which is the basic time unit used by ZooKeeper, as measured in milliseconds. It is used to regulate heartbeats, and timeouts |
| `zookeeper_maxclientcnxns`        | `10`                         | Limits the number of concurrent connections (at the socket level) that a single client, identified by IP address, may make to a single member of the ZooKeeper ensemble |
| `zookeeper_data_dir`              | `/var/lib/zookeeper`         | The location where ZooKeeper will store the in-memory database snapshots and, unless specified otherwise, the transaction log of updates to the database |
| `zookeeper_datalog_dir`           | `{{ zookeeper_data_dir }}`   | This option will direct the machine to write the transaction log to the `dataLogDir` rather than the `dataDir`. This allows a dedicated log device to be used, and helps avoid competition between logging and snaphots |
| `zookeeper_log_dir`               | `/var/log/zookeeper`         | Defines the Zookeeper log directory                              |
| `zookeeper_clientport`            | `2181`                       | The port to listen for client connections                        |
| `zookeeper_clientportaddress`     | `0.0.0.0`                    | The address (ipv4, ipv6 or hostname) to listen for client connections |
| `zookeeper_autopurge_snapretaincount`| `3`                       | When enabled, ZooKeeper auto purge feature retains the autopurge.snapRetainCount most recent snapshots and the corresponding transaction logs in the dataDir and dataLogDir respectively and deletes the rest |
| `zookeeper_autopurge_purgeinterval`| `0`                         | The time interval in hours for which the purge task has to be triggered. Set to a positive integer (1 and above) to enable the auto purging |
| `zookeeper_extra_env_vars`        | `[]`                         | List of environment variables to pass to Zookeeper (see [examples](../README.md#examples) below) |

[Return to main page](../README.md)
