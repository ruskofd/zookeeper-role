### General

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `zookeeper_version`               | `3.8.0`                      | Defines the version of Zookeeper to install                      |
| `zookeeper_user`                  | `zookeeper`                  | Defines the user to use to run Zookeeper service                 |
| `zookeeper_group`                 | `zookeeper`                  | Defines the user group to use to run Zookeeper service           |
| `zookeeper_install_dir`           | `/usr/local/zookeeper-{{ zookeeper_version }}`| Defines the installation directory of Zookeeper |
| `zookeeper_current_dir`           | `/usr/local/zookeeper`       | Defines the symlink to the current installation Zookeeper directory |
| `zookeeper_config_dir`            | `/etc/zookeeper`             | Defines the configuration directory of Zookeeper                 |
| `zookeeper_java_pkg_install`      | `true`                       | By default, the role will install a compatible version of Java (OpenJDK) for Zookeeper. If you want more control on how you want to install Java, set this variable to `false` |
| `zookeeper_java_pkg_version`      | `17`                         | Defines the version of Java (OpenJDK) to install for Zookeeper (check version compatible with your Zookeeper version) |

[Return to main page](../README.md)
