### Admin Server

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `zookeeper_adminserver_enabled`   | `true`                       | If set to `true`, enable the Zookeeper admin server              |
| `zookeeper_adminserver_address`   | `0.0.0.0`                    | The address the embedded Jetty server listens on                 |
| `zookeeper_adminserver_port`      | `8080`                       | The port the embedded Jetty server listens on                    |
| `zookeeper_adminserver_idletimeout`| `30000`                     | Set the maximum idle time in milliseconds that a connection can wait before sending or receiving data |
| `zookeeper_adminserver_commandurl` | `/commands`                 | The URL for listing and issuing commands relative to the root URL |

[Return to main page](../README.md)
