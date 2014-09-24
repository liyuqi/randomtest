randomtest
==========


```bash
$ sudo tar -xzf jdk-7u67-linux-x64.tar.gz
$ sudo cp -r jdk1.7.0_67/ /usr/lib/java/jdk1.7.0_67

$ sudo vi /etc/profile

export JAVA_HOME=/usr/lib/java/jdk1.7.0_67
export PATH=$PATH:$JAVA_HOME/bin
export CLASSPATH=$CLASSPATH:.:$JAVA_HOME/lib:$JAVA_HOME/jre/lib
```

```xml
<?xml version="1.0"?>
<!--
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->
<configuration>

<!-- Site specific YARN configuration properties -->
 <property>
        <name>yarn.resourcemanager.hostname</name>
        <value>btserver1</value>
 </property>
  <property>
    <name>yarn.resourcemanager.scheduler.class</name>
    <value>org.apache.hadoop.yarn.server.resourcemanager.scheduler.capacity.CapacityScheduler</value>
  </property>
    <property>
    <name>yarn.resourcemanager.scheduler.address</name>
    <value>btserver1:8030</value>
  </property>
    <property>
    <name>yarn.resourcemanager.resource-tracker.address</name>
    <value>btserver1:8031</value>
  </property>
  <property>
    <name>yarn.resourcemanager.address</name>
    <value>btserver1:8032</value>
  </property>
 
  <property>
        <name>yarn.nodemanager.aux-services.mapreduce_shuffle.class</name>
        <value>org.apache.hadoop.mapred.ShuffleHandler</value>
  </property>

  <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
  </property>
<!---->
  <property>
    <name>yarn.nodemanager.address</name>
    <value>0.0.0.0:8034</value>
  </property>
  <property>
    <name>yarn.nodemanager.local-dirs</name>
    <value>${hadoop.tmp.dir}/nodemanager/local</value>
  </property>
  <property>
    <name>yarn.nodemanager.remote-app-log-dir</name>
    <value>${hadoop.tmp.dir}/nodemanager/remote</value>
  </property>
  <property>
    <name>yarn.nodemanager.log-dirs</name>
    <value>${hadoop.tmp.dir}/nodemanager/logs</value>
  </property>
<!-- -->
</configuration>
```
