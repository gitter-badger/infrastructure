## Start Hadoop Cluster

The original script can be found [here](https://github.com/esse-io/el-data-platform/blob/master/bin/start-hd.sh)

	#!/bin/bash
	
	#on bd001
	hadoop-daemon.sh --script hdfs start namenode
	
	
	# 1-3
	for i in {1..3}; do ssh bd00$i "hadoop-daemon.sh --script hdfs start datanode"; done
	
	# bd001
	yarn-daemon.sh start resourcemanager
	
	# 1-3
	for i in {1..3}; do ssh bd00$i "yarn-daemon.sh start nodemanager"; done
