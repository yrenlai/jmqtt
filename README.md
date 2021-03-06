**English** | [中文](README_CN.md)
##  Jmqtt

**Note**：The `master` branch may be unstable during development, causing the packaged files to not run or even package. Please use the [releases](https://github.com/Cicizz/jmqtt/releases)  version. 

![Jmqtt logo](jmqtt.png)

## Features

* Developed in Java and Netty, it supports plug-in mode with high performance and high scalability.
* Support mqtt protocol qos0, qos1, qos2 message quality service.
* Supports cleansession, retain, will and other message services in the mqtt protocol.
* Full support for mqtt Topic match filtering.
* Support websocket protocol.
* Support RocksDB for data local storage to make data highly reliable.

## Quick Start

Online test environment：`120.24.69.113`，TCP port ：`1883`；Websocket port：`1884`.

1. Download the [release](https://github.com/Cicizz/jmqtt/releases) version or `clone` this project.
2. Execute in the root directory：`mvn -Ppackage-all -DskipTests clean install -U`
3. Run the jmqttstart script directly in the `jmqtt-distrubution/target/jmqtt/bin` directory.
4. Local launch: find the BrokerStartup class and configure the startup environment variable: The key is `JMQTT_HOME`, and the value is the absolute address where `jmqtt-distribution` is located. The purpose of the configuration is to specify the address where the jmqtt configuration file and log configuration file are located.


## Architecture Design

![架构图](jmqtt%20design.jpg)
## Module introduction and local environment

* **broker**：Mqtt protocol layer. logical processing. BrokerStartup is the startup class, BrokerController is the initialization class, initialize all the necessary environment, where the plugin configuration of acl, store must also be initialized here.
* **common**：Common layer. Used to store tool classes, bean classes, etc.
* **remoting**：Communication layer. Used for connection management, protocol analysis, heartbeat, etc.
* **distribution**：Configuration module. Used for configuration files, start and stop commands, etc.
* **example**：Client example. Only java and websocket examples are supported currently.
* **group**：Cluster management module. Used for message transmission, cluster management, and related operation and maintenance functions.
* **store**：Storage module. Provides several interfaces for mqtt protocol data, supports memory-based and Rocksdb local storage.

## RoadMap

### Version 3.x

1. Support simple operation and maintenance functions.
2. Support RocketMQ Bridge.
3. Support Kafka Bridge.
4. Support $SYS Topic Monitoring.

### Version 2.x

1. Support clustering, multi-host scale-out, high availability.
2. Support SSL/TLS.
3. Support safety certificate.

### Version 1.1.0

1. Add connect, publish, subsribe permission authentication interface and make it pluggable.
2. Remove Redis storage.
3. Optimize Rocksdb local storage.
4. Fix bugs in the subscription module.
5. Fix bugs that offline messages can't receive.
6. Fix bugs that occasionally do not receive retain messages.
7. Add storeLog, remotingLog messageTraceLog, clientTraceLog.

### Version 1.0.0

1. Full support for the mqtt protocol.
2. Support Websocket protocol.
3. Support for data local persistence

## Welcome to WeChat Subscription to communicate

![开发大小事](zze.jpg)