## Start Hadoop Cluster


	#!/bin/bash
	
	#on bd001
	set PATH=/docker/opt/apache-cassandra-2.1.6/bin
	cd $PATH
	./cassandre
	
	# 1-3
	for i in {1..3}; do ssh bd00$i "cd $PATH; ./cassandre"; done
