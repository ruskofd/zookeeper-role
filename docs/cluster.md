### Cluster options

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `zookeeper_cluster_mode_enabled`  | `false`                      | If set to `true`, enable some options in the configuration file to use Zookeeper in cluster mode |
| `zookeeper_id`                    | `1`                          | Defines the Zookeeper instance ID. The ID must be unique within the ensemble and should have a value between `1` and `255` |
| `zookeeper_servers`               | `{}`                         | List of dict to define Zookeeper ensemble members (see [examples](../README.md#examples)) |
| `zookeeper_initlimit`             | `5`                          | Amount of time, in ticks, to allow followers to connect and sync to a leader |
| `zookeeper_synclimit`             | `2`                          | Amount of time, in ticks, to allow followers to sync with ZooKeeper |

[Return to main page](../README.md)
