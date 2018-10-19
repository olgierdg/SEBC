# Run the terasort program as raffles using /user/raffles/tgen512m

```
[raffles@ip-172-31-16-185 ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/raffles/tgen512 /user/raffles/tsort512
18/10/19 09:23:08 INFO terasort.TeraSort: starting
18/10/19 09:23:09 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@OLGIERDG.SG, renewer=yarn, realUser=, issueDate=1539940989694, maxDate=1540545789694, sequenceNumber=1, masterKeyId=2 on 172.31.16.185:8020
18/10/19 09:23:09 INFO security.TokenCache: Got dt for hdfs://ip-172-31-16-185.eu-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.185:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@OLGIERDG.SG, renewer=yarn, realUser=, issueDate=1539940989694, maxDate=1540545789694, sequenceNumber=1, masterKeyId=2)
18/10/19 09:23:09 INFO input.FileInputFormat: Total input paths to process : 6
Spent 368ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 373ms
Sampling 10 splits of 156
Making 8 from 100000 sampled records
Computing parititions took 646ms
Spent 1021ms computing partitions.
18/10/19 09:23:10 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-185.eu-west-2.compute.internal/172.31.16.185:8032
18/10/19 09:23:10 INFO mapreduce.JobSubmitter: number of splits:156
18/10/19 09:23:11 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539940878356_0001
18/10/19 09:23:11 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.185:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@OLGIERDG.SG, renewer=yarn, realUser=, issueDate=1539940989694, maxDate=1540545789694, sequenceNumber=1, masterKeyId=2)
18/10/19 09:23:12 INFO impl.YarnClientImpl: Submitted application application_1539940878356_0001
18/10/19 09:23:12 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-185.eu-west-2.compute.internal:8088/proxy/application_1539940878356_0001/
18/10/19 09:23:12 INFO mapreduce.Job: Running job: job_1539940878356_0001
18/10/19 09:23:22 INFO mapreduce.Job: Job job_1539940878356_0001 running in uber mode : false
18/10/19 09:23:22 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:23:28 INFO mapreduce.Job:  map 1% reduce 0%
18/10/19 09:23:33 INFO mapreduce.Job:  map 2% reduce 0%
18/10/19 09:23:34 INFO mapreduce.Job:  map 4% reduce 0%
18/10/19 09:23:37 INFO mapreduce.Job:  map 6% reduce 0%
18/10/19 09:23:40 INFO mapreduce.Job:  map 9% reduce 0%
18/10/19 09:23:45 INFO mapreduce.Job:  map 11% reduce 0%
18/10/19 09:23:46 INFO mapreduce.Job:  map 12% reduce 0%
18/10/19 09:23:47 INFO mapreduce.Job:  map 14% reduce 0%
18/10/19 09:23:50 INFO mapreduce.Job:  map 15% reduce 0%
18/10/19 09:23:53 INFO mapreduce.Job:  map 16% reduce 0%
18/10/19 09:23:54 INFO mapreduce.Job:  map 19% reduce 0%
18/10/19 09:23:55 INFO mapreduce.Job:  map 20% reduce 0%
18/10/19 09:23:58 INFO mapreduce.Job:  map 21% reduce 0%
18/10/19 09:23:59 INFO mapreduce.Job:  map 22% reduce 0%
18/10/19 09:24:01 INFO mapreduce.Job:  map 23% reduce 0%
18/10/19 09:24:02 INFO mapreduce.Job:  map 24% reduce 0%
18/10/19 09:24:03 INFO mapreduce.Job:  map 25% reduce 0%
18/10/19 09:24:04 INFO mapreduce.Job:  map 26% reduce 0%
18/10/19 09:24:06 INFO mapreduce.Job:  map 27% reduce 0%
18/10/19 09:24:07 INFO mapreduce.Job:  map 28% reduce 0%
18/10/19 09:24:10 INFO mapreduce.Job:  map 29% reduce 0%
18/10/19 09:24:11 INFO mapreduce.Job:  map 31% reduce 0%
18/10/19 09:24:12 INFO mapreduce.Job:  map 33% reduce 0%
18/10/19 09:24:15 INFO mapreduce.Job:  map 34% reduce 0%
18/10/19 09:24:16 INFO mapreduce.Job:  map 35% reduce 0%
18/10/19 09:24:18 INFO mapreduce.Job:  map 36% reduce 0%
18/10/19 09:24:19 INFO mapreduce.Job:  map 37% reduce 0%
18/10/19 09:24:21 INFO mapreduce.Job:  map 39% reduce 0%
18/10/19 09:24:23 INFO mapreduce.Job:  map 40% reduce 0%
18/10/19 09:24:25 INFO mapreduce.Job:  map 41% reduce 0%
18/10/19 09:24:26 INFO mapreduce.Job:  map 42% reduce 0%
18/10/19 09:24:27 INFO mapreduce.Job:  map 44% reduce 0%
18/10/19 09:24:29 INFO mapreduce.Job:  map 45% reduce 0%
18/10/19 09:24:30 INFO mapreduce.Job:  map 46% reduce 0%
18/10/19 09:24:31 INFO mapreduce.Job:  map 47% reduce 0%
18/10/19 09:24:34 INFO mapreduce.Job:  map 48% reduce 0%
18/10/19 09:24:35 INFO mapreduce.Job:  map 50% reduce 0%
18/10/19 09:24:36 INFO mapreduce.Job:  map 51% reduce 0%
18/10/19 09:24:38 INFO mapreduce.Job:  map 52% reduce 0%
18/10/19 09:24:40 INFO mapreduce.Job:  map 53% reduce 0%
18/10/19 09:24:41 INFO mapreduce.Job:  map 54% reduce 0%
18/10/19 09:24:43 INFO mapreduce.Job:  map 56% reduce 0%
18/10/19 09:24:45 INFO mapreduce.Job:  map 57% reduce 0%
18/10/19 09:24:46 INFO mapreduce.Job:  map 58% reduce 0%
18/10/19 09:24:48 INFO mapreduce.Job:  map 59% reduce 0%
18/10/19 09:24:49 INFO mapreduce.Job:  map 60% reduce 0%
18/10/19 09:24:50 INFO mapreduce.Job:  map 62% reduce 0%
18/10/19 09:24:53 INFO mapreduce.Job:  map 63% reduce 0%
18/10/19 09:24:54 INFO mapreduce.Job:  map 65% reduce 0%
18/10/19 09:24:57 INFO mapreduce.Job:  map 67% reduce 0%
18/10/19 09:25:00 INFO mapreduce.Job:  map 70% reduce 0%
18/10/19 09:25:02 INFO mapreduce.Job:  map 71% reduce 0%
18/10/19 09:25:05 INFO mapreduce.Job:  map 73% reduce 0%
18/10/19 09:25:06 INFO mapreduce.Job:  map 74% reduce 0%
18/10/19 09:25:09 INFO mapreduce.Job:  map 75% reduce 0%
18/10/19 09:25:10 INFO mapreduce.Job:  map 77% reduce 0%
18/10/19 09:25:11 INFO mapreduce.Job:  map 78% reduce 0%
18/10/19 09:25:13 INFO mapreduce.Job:  map 79% reduce 0%
18/10/19 09:25:15 INFO mapreduce.Job:  map 80% reduce 0%
18/10/19 09:25:16 INFO mapreduce.Job:  map 81% reduce 0%
18/10/19 09:25:17 INFO mapreduce.Job:  map 82% reduce 0%
18/10/19 09:25:19 INFO mapreduce.Job:  map 83% reduce 0%
18/10/19 09:25:20 INFO mapreduce.Job:  map 85% reduce 0%
18/10/19 09:25:24 INFO mapreduce.Job:  map 87% reduce 0%
18/10/19 09:25:30 INFO mapreduce.Job:  map 88% reduce 0%
18/10/19 09:25:31 INFO mapreduce.Job:  map 89% reduce 0%
18/10/19 09:25:33 INFO mapreduce.Job:  map 90% reduce 0%
18/10/19 09:25:36 INFO mapreduce.Job:  map 91% reduce 4%
18/10/19 09:25:37 INFO mapreduce.Job:  map 92% reduce 11%
18/10/19 09:25:38 INFO mapreduce.Job:  map 92% reduce 15%
18/10/19 09:25:41 INFO mapreduce.Job:  map 93% reduce 15%
18/10/19 09:25:42 INFO mapreduce.Job:  map 94% reduce 15%
18/10/19 09:25:44 INFO mapreduce.Job:  map 94% reduce 16%
18/10/19 09:25:46 INFO mapreduce.Job:  map 96% reduce 16%
18/10/19 09:25:49 INFO mapreduce.Job:  map 97% reduce 16%
18/10/19 09:25:51 INFO mapreduce.Job:  map 98% reduce 16%
18/10/19 09:25:52 INFO mapreduce.Job:  map 99% reduce 16%
18/10/19 09:25:56 INFO mapreduce.Job:  map 100% reduce 16%
18/10/19 09:26:01 INFO mapreduce.Job:  map 100% reduce 30%
18/10/19 09:26:02 INFO mapreduce.Job:  map 100% reduce 34%
18/10/19 09:26:06 INFO mapreduce.Job:  map 100% reduce 38%
18/10/19 09:26:07 INFO mapreduce.Job:  map 100% reduce 44%
18/10/19 09:26:08 INFO mapreduce.Job:  map 100% reduce 56%
18/10/19 09:26:09 INFO mapreduce.Job:  map 100% reduce 67%
18/10/19 09:26:10 INFO mapreduce.Job:  map 100% reduce 68%
18/10/19 09:26:12 INFO mapreduce.Job:  map 100% reduce 78%
18/10/19 09:26:14 INFO mapreduce.Job:  map 100% reduce 83%
18/10/19 09:26:15 INFO mapreduce.Job:  map 100% reduce 92%
18/10/19 09:26:18 INFO mapreduce.Job:  map 100% reduce 94%
18/10/19 09:26:21 INFO mapreduce.Job:  map 100% reduce 96%
18/10/19 09:26:22 INFO mapreduce.Job:  map 100% reduce 98%
18/10/19 09:26:24 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:26:24 INFO mapreduce.Job: Job job_1539940878356_0001 completed successfully
18/10/19 09:26:24 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=2286373137
		FILE: Number of bytes written=4551409549
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=5120024024
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=492
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters
		Launched map tasks=156
		Launched reduce tasks=8
		Data-local map tasks=155
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=913633
		Total time spent by all reduces in occupied slots (ms)=284517
		Total time spent by all map tasks (ms)=913633
		Total time spent by all reduce tasks (ms)=284517
		Total vcore-milliseconds taken by all map tasks=913633
		Total vcore-milliseconds taken by all reduce tasks=284517
		Total megabyte-milliseconds taken by all map tasks=935560192
		Total megabyte-milliseconds taken by all reduce tasks=291345408
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Map output bytes=5222400000
		Map output materialized bytes=2240103638
		Input split bytes=24024
		Combine input records=0
		Combine output records=0
		Reduce input groups=51200000
		Reduce shuffle bytes=2240103638
		Reduce input records=51200000
		Reduce output records=51200000
		Spilled Records=102400000
		Shuffled Maps =1248
		Failed Shuffles=0
		Merged Map outputs=1248
		GC time elapsed (ms)=20695
		CPU time spent (ms)=743580
		Physical memory (bytes) snapshot=82381234176
		Virtual memory (bytes) snapshot=455496454144
		Total committed heap usage (bytes)=84203798528
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=5120000000
	File Output Format Counters
		Bytes Written=5120000000
18/10/19 09:26:24 INFO terasort.TeraSort: done
```