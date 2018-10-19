# Run the Hadoop pi program as the user fullerton

```
[fullerton@ip-172-31-16-185 ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 16 1000
Number of Maps  = 16
Samples per Map = 1000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Starting Job
18/10/19 09:26:54 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-185.eu-west-2.compute.internal/172.31.16.185:8032
18/10/19 09:26:54 INFO hdfs.DFSClient: Created token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@OLGIERDG.SG, renewer=yarn, realUser=, issueDate=1539941214243, maxDate=1540546014243, sequenceNumber=2, masterKeyId=2 on 172.31.16.185:8020
18/10/19 09:26:54 INFO security.TokenCache: Got dt for hdfs://ip-172-31-16-185.eu-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.185:8020, Ident: (token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@OLGIERDG.SG, renewer=yarn, realUser=, issueDate=1539941214243, maxDate=1540546014243, sequenceNumber=2, masterKeyId=2)
18/10/19 09:26:54 INFO input.FileInputFormat: Total input paths to process : 16
18/10/19 09:26:54 INFO mapreduce.JobSubmitter: number of splits:16
18/10/19 09:26:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539940878356_0002
18/10/19 09:26:54 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.185:8020, Ident: (token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@OLGIERDG.SG, renewer=yarn, realUser=, issueDate=1539941214243, maxDate=1540546014243, sequenceNumber=2, masterKeyId=2)
18/10/19 09:26:54 INFO impl.YarnClientImpl: Submitted application application_1539940878356_0002
18/10/19 09:26:54 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-185.eu-west-2.compute.internal:8088/proxy/application_1539940878356_0002/
18/10/19 09:26:54 INFO mapreduce.Job: Running job: job_1539940878356_0002
18/10/19 09:27:03 INFO mapreduce.Job: Job job_1539940878356_0002 running in uber mode : false
18/10/19 09:27:03 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:27:09 INFO mapreduce.Job:  map 6% reduce 0%
18/10/19 09:27:12 INFO mapreduce.Job:  map 19% reduce 0%
18/10/19 09:27:13 INFO mapreduce.Job:  map 31% reduce 0%
18/10/19 09:27:14 INFO mapreduce.Job:  map 44% reduce 0%
18/10/19 09:27:15 INFO mapreduce.Job:  map 56% reduce 0%
18/10/19 09:27:17 INFO mapreduce.Job:  map 69% reduce 0%
18/10/19 09:27:18 INFO mapreduce.Job:  map 81% reduce 0%
18/10/19 09:27:19 INFO mapreduce.Job:  map 100% reduce 0%
18/10/19 09:27:23 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:27:23 INFO mapreduce.Job: Job job_1539940878356_0002 completed successfully
18/10/19 09:27:23 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=132
		FILE: Number of bytes written=2569820
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=4838
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=67
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters
		Launched map tasks=16
		Launched reduce tasks=1
		Data-local map tasks=16
		Total time spent by all maps in occupied slots (ms)=87725
		Total time spent by all reduces in occupied slots (ms)=2866
		Total time spent by all map tasks (ms)=87725
		Total time spent by all reduce tasks (ms)=2866
		Total vcore-milliseconds taken by all map tasks=87725
		Total vcore-milliseconds taken by all reduce tasks=2866
		Total megabyte-milliseconds taken by all map tasks=89830400
		Total megabyte-milliseconds taken by all reduce tasks=2934784
	Map-Reduce Framework
		Map input records=16
		Map output records=32
		Map output bytes=288
		Map output materialized bytes=544
		Input split bytes=2950
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=544
		Reduce input records=32
		Reduce output records=0
		Spilled Records=64
		Shuffled Maps =16
		Failed Shuffles=0
		Merged Map outputs=16
		GC time elapsed (ms)=1403
		CPU time spent (ms)=12890
		Physical memory (bytes) snapshot=7600742400
		Virtual memory (bytes) snapshot=47195291648
		Total committed heap usage (bytes)=8036286464
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=1888
	File Output Format Counters
		Bytes Written=97
Job Finished in 29.569 seconds
Estimated value of Pi is 3.14250000000000000000
```