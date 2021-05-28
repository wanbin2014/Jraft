# SimpleRaft

refer to ：https://raft.github.io/raft.pdf

## 实现的功能
### leader election
### log replication

server
<code>
  mvn compile exec:java -Dexec.mainClass="com.wanbin.simpleRaft.SimpleRaftServer" -Dexec.args="-i 127.0.0.1 -p 3001 -m 127.0.0.3001,127.0.0.1:3002,127.0.0.1:3003,127.0.0.1:3004"
</code>

<code>
  mvn compile exec:java -Dexec.mainClass="com.wanbin.simpleRaft.SimpleRaftServer" -Dexec.args="-i 127.0.0.1 -p 3002 -m 127.0.0.3001,127.0.0.1:3002,127.0.0.1:3003,127.0.0.1:3004"
</code>

<code>
  mvn compile exec:java -Dexec.mainClass="com.wanbin.simpleRaft.SimpleRaftServer" -Dexec.args="-i 127.0.0.1 -p 3003 -m 127.0.0.3001,127.0.0.1:3002,127.0.0.1:3003,127.0.0.1:3004"
</code>

<code>
  mvn compile exec:java -Dexec.mainClass="com.wanbin.simpleRaft.SimpleRaftServer" -Dexec.args="-i 127.0.0.1 -p 3004 -m 127.0.0.3001,127.0.0.1:3002,127.0.0.1:3003,127.0.0.1:3004"
</code>

client
<code>
 mvn compile exec:java -Dexec.mainClass="com.wanbin.simpleRaft.client.SimpleRaftClient" -Dexec.args="-i 127.0.0.1 -p 3002 -c "add world3""
 </code>
