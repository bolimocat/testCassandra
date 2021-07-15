# testCassandra
使用java编写的cassandra测试工具，某项目中想使用cassandra作为批量采集数据的存储端，想对cassandra的快速存储能力进行验证，实际是想把cassandra做IoT库来用，当然基于c的时序库，有Ka的方案。
当前工具基于的是cassandra2.1.*
运行方法：
java -jar testCassandra ./file/cassandraStressPara

配置文件名称可以修改，内容：
host:192.168.130.15
user:cassandra
pass:cassandra
ksname:test_ks //自动创建的key space name
threads:16 //并发线程数
devices:20 //设备数，这里实际是表的数量
sensors:100 //传感器数，即表里的字段数，默认为整形2位随机数。
times:50 //所有线程重复次数。

后续可以增加数据类型的修改等，当然现在所以IoT的思路使用cassandra，本身并不是他的实际用途。

执行过程中会统计写入的次数和消耗的总时间（毫秒），最终用于计算每个点写入的平均时间。
