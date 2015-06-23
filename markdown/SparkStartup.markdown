## Start Spark Cluster

	#!/bin/bash
	
	#on bd001
	cd /docker/opt/spark-1.4.0-bin-hadoop2.6/sbin
	./stop-master.sh
	./start-master.sh
	
	
	# 1-3
	for i in {1..3}; do scp /docker/opt/spark-1.4.0-bin-hadoop2.6/conf/spark-env.sh \
		bd00$i:/docker/opt/spark-1.4.0-bin-hadoop2.6/conf/; \
		ssh bd00$i "cd /docker/opt/spark-1.4.0-bin-hadoop2.6/sbin; ./stop-slave.sh; \
		./start-slave.sh spark://bd001.eloancn.com:7077"; \
		done
	
