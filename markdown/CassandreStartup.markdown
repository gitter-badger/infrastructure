## Start Hadoop Cluster

You need to verify the variables in [conf/cassandra.yaml](/conf/cassandra/cassandra.yaml). In our case, we separate Cassandra data in a specific location, to avoid huge data growth breaking the partition in production.

	#!/bin/bash
	
	#on bd001
	set PATH=/docker/opt/apache-cassandra-2.1.6/bin
	cd $PATH
	./cassandre
	
	# 1-3
	for i in {1..3}; do ssh bd00$i "cd $PATH; ./cassandre"; done
