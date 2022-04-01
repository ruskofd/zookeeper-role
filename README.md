<p><img src="https://upload.wikimedia.org/wikipedia/commons/7/77/Apache_ZooKeeper_logo.svg" alt="etcd-logo" title="etcd" align="top" height=190 /></p>

*Apache ZooKeeper is an effort to develop and maintain an open-source server which enables highly reliable distributed coordination. ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services.*

### General informations

This Ansible role is designed to deploy and manage Apache Zookeeper instances but also for bootstraping multi-nodes clusters.

**Table of Contents**

  - [Roles variables](#role-variables)
  - [Examples](#examples)
  - [Install and use this role](#install-and-use-this-role)

**Supported Platforms**

  - CentOS/RHEL 8
  - Fedora 35

**References**

  - Apache Zookeeper : https://zookeeper.apache.org/

### Role variables

The role variables are available here :

  - [General](docs/general.md)
  - [Global options](docs/global.md)
  - [Cluster options](docs/cluster.md)
  - [Admin Server](docs/adminserver.md)

### Role tags

This role has some tags that you can use for some operations without replaying the entire role :

  - `zk_install`: create Zookeeper user, install Java (optional) and install Zookeeper binaries
  - `zk_config`: create the required directories for Zookeeper operations and apply configuration
  - `zk_service`: deliver a service systemd unit for Zookeeper and ensure Zookeeper is started and enabled on boot

### Examples

* **Create a Zookeeper ensemble (cluster)**

  To create a Zookeeper ensemble, you need at least 3 nodes. Firstly, define the Zookeeper instance ID through the `zookeeper_id` on all hosts (each node should have a unique id) :

  ```YAML
  # Node 1
  zookeeper_id: 1

  # Node 2
  zookeeper_id: 2

  # Node 3
  zookeeper_id: 3
  ```

  To create cluster, you must define all the servers that will constitute the Zookeeper ensemble in the `zookeeper_servers` variable :

  ```YAML
  zookeeper_cluster_mode_enabled: true
  zookeeper_servers:
    - { id: 1, host: 10.0.122.10, peer_port: 2888, election_port: 3888 } # node 1
    - { id: 2, host: 10.0.122.11, peer_port: 2888, election_port: 3888 } # node 2
    - { id: 3, host: 10.0.122.13, peer_port: 2888, election_port: 3888 } # node 3
  ```

  The ID must match the `zookeeper_id` variable of each node.

* **Extra environment variables**

  You can define extra environment variables to pass to Zookeeper using the `zookeeper_extra_env_vars` variable :

  ```YAML
  ---
  zookeeper_extra_env_vars:
    - "VAR=VALUE" 
  ```

### Install and use this role

* Install the role using the command-line

  ```shell
  $ ansible-galaxy role install git+https://github.com/ruskofd/zookeeper-role.git
  ```

* Install the role in your projects using a `requirements.yml` file and `ansible-galaxy` command-line

  ```YAML
  $ cat requirements.yml
  roles:
    - name: zookeeper
      src: https://github.com/ruskofd/zookeeper-role.git
      scm: git
      version: 1.0.0

  $ ansible-galaxy install -f -r requirements.yml
  ```

* Once the role is installed, you can use it in your playbooks

  ```YAML
  - name: Install Zookeeper
    hosts: zookeeper
    roles:
      - role: zookeeper
  ```
