# Create an end-user Linux account named with your GitHub handle

```
bash-4.4$ ansible -i hosts all --user centos --private-key /Users/o.grodzki/.ssh/olaf-keypair.pem -c paramiko --become -m shell -a 'useradd olgierdg'
ec2-18-196-102-174.eu-central-1.compute.amazonaws.com | CHANGED | rc=0 >>


ec2-35-157-195-83.eu-central-1.compute.amazonaws.com | CHANGED | rc=0 >>


ec2-35-159-51-248.eu-central-1.compute.amazonaws.com | CHANGED | rc=0 >>


ec2-3-120-225-216.eu-central-1.compute.amazonaws.com | CHANGED | rc=0 >>


ec2-3-120-244-147.eu-central-1.compute.amazonaws.com | CHANGED | rc=0 >>
```

# Create a home HDFS directory for this user as well

```
[hdfs@ip-172-31-46-123 ~]$ hadoop fs -mkdir /user/olgierdg
[hdfs@ip-172-31-46-123 ~]$ hadoop fs -chmod 755 /user/olgierdg
[hdfs@ip-172-31-46-123 ~]$ hadoop fs -chown olgierdg:olgierdg /user/olgierdg
```
# Teragen

```
[olgierdg@ip-172-31-46-123 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 100000000 /user/olgierdg/teragen
18/10/16 09:18:15 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-35-238.eu-central-1.compute.internal/172.31.35.238:8032
18/10/16 09:18:16 INFO terasort.TeraSort: Generating 100000000 using 4
18/10/16 09:18:16 INFO mapreduce.JobSubmitter: number of splits:4
18/10/16 09:18:16 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
18/10/16 09:18:16 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
18/10/16 09:18:16 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539675657977_0006
18/10/16 09:18:16 INFO impl.YarnClientImpl: Submitted application application_1539675657977_0006
18/10/16 09:18:16 INFO mapreduce.Job: The url to track the job: http://ip-172-31-35-238.eu-central-1.compute.internal:8088/proxy/application_1539675657977_0006/
18/10/16 09:18:16 INFO mapreduce.Job: Running job: job_1539675657977_0006
18/10/16 09:18:21 INFO mapreduce.Job: Job job_1539675657977_0006 running in uber mode : false
18/10/16 09:18:21 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 09:18:31 INFO mapreduce.Job:  map 11% reduce 0%
18/10/16 09:18:32 INFO mapreduce.Job:  map 16% reduce 0%
18/10/16 09:18:34 INFO mapreduce.Job:  map 18% reduce 0%
18/10/16 09:18:35 INFO mapreduce.Job:  map 21% reduce 0%
18/10/16 09:18:37 INFO mapreduce.Job:  map 24% reduce 0%
18/10/16 09:18:38 INFO mapreduce.Job:  map 26% reduce 0%
18/10/16 09:18:41 INFO mapreduce.Job:  map 29% reduce 0%
18/10/16 09:18:42 INFO mapreduce.Job:  map 32% reduce 0%
18/10/16 09:18:44 INFO mapreduce.Job:  map 35% reduce 0%
18/10/16 09:18:45 INFO mapreduce.Job:  map 38% reduce 0%
18/10/16 09:18:47 INFO mapreduce.Job:  map 40% reduce 0%
18/10/16 09:18:48 INFO mapreduce.Job:  map 43% reduce 0%
18/10/16 09:18:50 INFO mapreduce.Job:  map 48% reduce 0%
18/10/16 09:18:53 INFO mapreduce.Job:  map 49% reduce 0%
18/10/16 09:18:56 INFO mapreduce.Job:  map 55% reduce 0%
18/10/16 09:18:59 INFO mapreduce.Job:  map 59% reduce 0%
18/10/16 09:19:02 INFO mapreduce.Job:  map 62% reduce 0%
18/10/16 09:19:05 INFO mapreduce.Job:  map 66% reduce 0%
18/10/16 09:19:08 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 09:19:11 INFO mapreduce.Job:  map 74% reduce 0%
18/10/16 09:19:14 INFO mapreduce.Job:  map 77% reduce 0%
18/10/16 09:19:17 INFO mapreduce.Job:  map 81% reduce 0%
18/10/16 09:19:20 INFO mapreduce.Job:  map 84% reduce 0%
18/10/16 09:19:23 INFO mapreduce.Job:  map 86% reduce 0%
18/10/16 09:19:24 INFO mapreduce.Job:  map 88% reduce 0%
18/10/16 09:19:26 INFO mapreduce.Job:  map 91% reduce 0%
18/10/16 09:19:29 INFO mapreduce.Job:  map 94% reduce 0%
18/10/16 09:19:30 INFO mapreduce.Job:  map 95% reduce 0%
18/10/16 09:19:32 INFO mapreduce.Job:  map 97% reduce 0%
18/10/16 09:19:33 INFO mapreduce.Job:  map 98% reduce 0%
18/10/16 09:19:35 INFO mapreduce.Job:  map 100% reduce 0%
18/10/16 09:19:37 INFO mapreduce.Job: Job job_1539675657977_0006 completed successfully
18/10/16 09:19:37 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=492328
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=274547
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=274547
                Total vcore-seconds taken by all map tasks=274547
                Total megabyte-seconds taken by all map tasks=281136128
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=565
                CPU time spent (ms)=145310
                Physical memory (bytes) snapshot=1370193920
                Virtual memory (bytes) snapshot=11120746496
                Total committed heap usage (bytes)=1049100288
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    1m23.839s
user    0m6.333s
sys     0m0.450s
[olgierdg@ip-172-31-46-123 ~]$
```

# Terasort

```
[olgierdg@ip-172-31-46-123 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/olgierdg/teragen /user/olgierdg/terasort
18/10/16 09:22:10 INFO terasort.TeraSort: starting
18/10/16 09:22:11 INFO input.FileInputFormat: Total input paths to process : 4
Spent 163ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 169ms
Sampling 10 splits of 300
Making 8 from 100000 sampled records
Computing parititions took 696ms
Spent 867ms computing partitions.
18/10/16 09:22:12 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-35-238.eu-central-1.compute.internal/172.31.35.238:8032
18/10/16 09:22:12 INFO mapreduce.JobSubmitter: number of splits:300
18/10/16 09:22:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539675657977_0007
18/10/16 09:22:13 INFO impl.YarnClientImpl: Submitted application application_1539675657977_0007
18/10/16 09:22:13 INFO mapreduce.Job: The url to track the job: http://ip-172-31-35-238.eu-central-1.compute.internal:8088/proxy/application_1539675657977_0007/
18/10/16 09:22:13 INFO mapreduce.Job: Running job: job_1539675657977_0007
18/10/16 09:22:18 INFO mapreduce.Job: Job job_1539675657977_0007 running in uber mode : false
18/10/16 09:22:18 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 09:22:25 INFO mapreduce.Job:  map 1% reduce 0%
18/10/16 09:22:26 INFO mapreduce.Job:  map 2% reduce 0%
18/10/16 09:22:29 INFO mapreduce.Job:  map 3% reduce 0%
18/10/16 09:22:32 INFO mapreduce.Job:  map 4% reduce 0%
18/10/16 09:22:33 INFO mapreduce.Job:  map 5% reduce 0%
18/10/16 09:22:38 INFO mapreduce.Job:  map 6% reduce 0%
18/10/16 09:22:39 INFO mapreduce.Job:  map 7% reduce 0%
18/10/16 09:22:44 INFO mapreduce.Job:  map 9% reduce 0%
18/10/16 09:22:46 INFO mapreduce.Job:  map 10% reduce 0%
18/10/16 09:22:50 INFO mapreduce.Job:  map 11% reduce 0%
18/10/16 09:22:51 INFO mapreduce.Job:  map 12% reduce 0%
18/10/16 09:22:56 INFO mapreduce.Job:  map 13% reduce 0%
18/10/16 09:22:57 INFO mapreduce.Job:  map 14% reduce 0%
18/10/16 09:22:59 INFO mapreduce.Job:  map 15% reduce 0%
18/10/16 09:23:03 INFO mapreduce.Job:  map 16% reduce 0%
18/10/16 09:23:05 INFO mapreduce.Job:  map 17% reduce 0%
18/10/16 09:23:08 INFO mapreduce.Job:  map 18% reduce 0%
18/10/16 09:23:09 INFO mapreduce.Job:  map 19% reduce 0%
18/10/16 09:23:14 INFO mapreduce.Job:  map 20% reduce 0%
18/10/16 09:23:15 INFO mapreduce.Job:  map 21% reduce 0%
18/10/16 09:23:18 INFO mapreduce.Job:  map 22% reduce 0%
18/10/16 09:23:20 INFO mapreduce.Job:  map 23% reduce 0%
18/10/16 09:23:23 INFO mapreduce.Job:  map 24% reduce 0%
18/10/16 09:23:26 INFO mapreduce.Job:  map 25% reduce 0%
18/10/16 09:23:27 INFO mapreduce.Job:  map 26% reduce 0%
18/10/16 09:23:30 INFO mapreduce.Job:  map 27% reduce 0%
18/10/16 09:23:33 INFO mapreduce.Job:  map 28% reduce 0%
18/10/16 09:23:35 INFO mapreduce.Job:  map 29% reduce 0%
18/10/16 09:23:38 INFO mapreduce.Job:  map 30% reduce 0%
18/10/16 09:23:39 INFO mapreduce.Job:  map 31% reduce 0%
18/10/16 09:23:43 INFO mapreduce.Job:  map 32% reduce 0%
18/10/16 09:23:45 INFO mapreduce.Job:  map 33% reduce 0%
18/10/16 09:23:48 INFO mapreduce.Job:  map 34% reduce 0%
18/10/16 09:23:50 INFO mapreduce.Job:  map 35% reduce 0%
18/10/16 09:23:53 INFO mapreduce.Job:  map 36% reduce 0%
18/10/16 09:23:56 INFO mapreduce.Job:  map 37% reduce 0%
18/10/16 09:23:57 INFO mapreduce.Job:  map 38% reduce 0%
18/10/16 09:24:00 INFO mapreduce.Job:  map 39% reduce 0%
18/10/16 09:24:03 INFO mapreduce.Job:  map 40% reduce 0%
18/10/16 09:24:05 INFO mapreduce.Job:  map 41% reduce 0%
18/10/16 09:24:08 INFO mapreduce.Job:  map 42% reduce 0%
18/10/16 09:24:10 INFO mapreduce.Job:  map 43% reduce 0%
18/10/16 09:24:13 INFO mapreduce.Job:  map 44% reduce 0%
18/10/16 09:24:15 INFO mapreduce.Job:  map 45% reduce 0%
18/10/16 09:24:19 INFO mapreduce.Job:  map 46% reduce 0%
18/10/16 09:24:22 INFO mapreduce.Job:  map 47% reduce 0%
18/10/16 09:24:24 INFO mapreduce.Job:  map 48% reduce 0%
18/10/16 09:24:27 INFO mapreduce.Job:  map 49% reduce 0%
18/10/16 09:24:29 INFO mapreduce.Job:  map 50% reduce 0%
18/10/16 09:24:31 INFO mapreduce.Job:  map 51% reduce 0%
18/10/16 09:24:34 INFO mapreduce.Job:  map 52% reduce 0%
18/10/16 09:24:36 INFO mapreduce.Job:  map 53% reduce 0%
18/10/16 09:24:39 INFO mapreduce.Job:  map 54% reduce 0%
18/10/16 09:24:41 INFO mapreduce.Job:  map 55% reduce 0%
18/10/16 09:24:44 INFO mapreduce.Job:  map 56% reduce 0%
18/10/16 09:24:46 INFO mapreduce.Job:  map 57% reduce 0%
18/10/16 09:24:49 INFO mapreduce.Job:  map 58% reduce 0%
18/10/16 09:24:52 INFO mapreduce.Job:  map 59% reduce 0%
18/10/16 09:24:54 INFO mapreduce.Job:  map 60% reduce 0%
18/10/16 09:24:57 INFO mapreduce.Job:  map 61% reduce 0%
18/10/16 09:24:59 INFO mapreduce.Job:  map 62% reduce 0%
18/10/16 09:25:01 INFO mapreduce.Job:  map 63% reduce 0%
18/10/16 09:25:04 INFO mapreduce.Job:  map 64% reduce 0%
18/10/16 09:25:06 INFO mapreduce.Job:  map 65% reduce 0%
18/10/16 09:25:09 INFO mapreduce.Job:  map 66% reduce 0%
18/10/16 09:25:11 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 09:25:14 INFO mapreduce.Job:  map 68% reduce 0%
18/10/16 09:25:17 INFO mapreduce.Job:  map 69% reduce 0%
18/10/16 09:25:19 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 09:25:22 INFO mapreduce.Job:  map 71% reduce 0%
18/10/16 09:25:24 INFO mapreduce.Job:  map 72% reduce 0%
18/10/16 09:25:27 INFO mapreduce.Job:  map 73% reduce 0%
18/10/16 09:25:29 INFO mapreduce.Job:  map 74% reduce 0%
18/10/16 09:25:31 INFO mapreduce.Job:  map 75% reduce 0%
18/10/16 09:25:34 INFO mapreduce.Job:  map 76% reduce 0%
18/10/16 09:25:36 INFO mapreduce.Job:  map 77% reduce 0%
18/10/16 09:25:39 INFO mapreduce.Job:  map 78% reduce 0%
18/10/16 09:25:42 INFO mapreduce.Job:  map 79% reduce 0%
18/10/16 09:25:44 INFO mapreduce.Job:  map 80% reduce 0%
18/10/16 09:25:47 INFO mapreduce.Job:  map 81% reduce 0%
18/10/16 09:25:49 INFO mapreduce.Job:  map 82% reduce 0%
18/10/16 09:25:54 INFO mapreduce.Job:  map 83% reduce 0%
18/10/16 09:25:56 INFO mapreduce.Job:  map 83% reduce 6%
18/10/16 09:25:57 INFO mapreduce.Job:  map 83% reduce 9%
18/10/16 09:25:58 INFO mapreduce.Job:  map 83% reduce 11%
18/10/16 09:25:59 INFO mapreduce.Job:  map 84% reduce 12%
18/10/16 09:26:00 INFO mapreduce.Job:  map 84% reduce 13%
18/10/16 09:26:01 INFO mapreduce.Job:  map 84% reduce 14%
18/10/16 09:26:04 INFO mapreduce.Job:  map 85% reduce 14%
18/10/16 09:26:09 INFO mapreduce.Job:  map 86% reduce 14%
18/10/16 09:26:14 INFO mapreduce.Job:  map 87% reduce 14%
18/10/16 09:26:19 INFO mapreduce.Job:  map 88% reduce 14%
18/10/16 09:26:20 INFO mapreduce.Job:  map 88% reduce 15%
18/10/16 09:26:24 INFO mapreduce.Job:  map 89% reduce 15%
18/10/16 09:26:29 INFO mapreduce.Job:  map 90% reduce 15%
18/10/16 09:26:34 INFO mapreduce.Job:  map 91% reduce 15%
18/10/16 09:26:39 INFO mapreduce.Job:  map 92% reduce 15%
18/10/16 09:26:44 INFO mapreduce.Job:  map 93% reduce 15%
18/10/16 09:26:49 INFO mapreduce.Job:  map 94% reduce 15%
18/10/16 09:26:50 INFO mapreduce.Job:  map 94% reduce 16%
18/10/16 09:26:54 INFO mapreduce.Job:  map 95% reduce 16%
18/10/16 09:26:59 INFO mapreduce.Job:  map 96% reduce 16%
18/10/16 09:27:04 INFO mapreduce.Job:  map 97% reduce 16%
18/10/16 09:27:09 INFO mapreduce.Job:  map 98% reduce 16%
18/10/16 09:27:14 INFO mapreduce.Job:  map 99% reduce 16%
18/10/16 09:27:18 INFO mapreduce.Job:  map 99% reduce 17%
18/10/16 09:27:19 INFO mapreduce.Job:  map 100% reduce 17%
18/10/16 09:27:23 INFO mapreduce.Job:  map 100% reduce 18%
18/10/16 09:27:24 INFO mapreduce.Job:  map 100% reduce 24%
18/10/16 09:27:25 INFO mapreduce.Job:  map 100% reduce 28%
18/10/16 09:27:26 INFO mapreduce.Job:  map 100% reduce 34%
18/10/16 09:27:27 INFO mapreduce.Job:  map 100% reduce 37%
18/10/16 09:27:28 INFO mapreduce.Job:  map 100% reduce 40%
18/10/16 09:27:29 INFO mapreduce.Job:  map 100% reduce 43%
18/10/16 09:27:30 INFO mapreduce.Job:  map 100% reduce 44%
18/10/16 09:27:31 INFO mapreduce.Job:  map 100% reduce 45%
18/10/16 09:27:32 INFO mapreduce.Job:  map 100% reduce 48%
18/10/16 09:27:33 INFO mapreduce.Job:  map 100% reduce 53%
18/10/16 09:27:34 INFO mapreduce.Job:  map 100% reduce 57%
18/10/16 09:27:35 INFO mapreduce.Job:  map 100% reduce 63%
18/10/16 09:27:36 INFO mapreduce.Job:  map 100% reduce 64%
18/10/16 09:27:37 INFO mapreduce.Job:  map 100% reduce 66%
18/10/16 09:27:38 INFO mapreduce.Job:  map 100% reduce 68%
18/10/16 09:27:39 INFO mapreduce.Job:  map 100% reduce 69%
18/10/16 09:27:40 INFO mapreduce.Job:  map 100% reduce 71%
18/10/16 09:27:41 INFO mapreduce.Job:  map 100% reduce 74%
18/10/16 09:27:42 INFO mapreduce.Job:  map 100% reduce 79%
18/10/16 09:27:43 INFO mapreduce.Job:  map 100% reduce 80%
18/10/16 09:27:44 INFO mapreduce.Job:  map 100% reduce 81%
18/10/16 09:27:45 INFO mapreduce.Job:  map 100% reduce 82%
18/10/16 09:27:46 INFO mapreduce.Job:  map 100% reduce 83%
18/10/16 09:27:47 INFO mapreduce.Job:  map 100% reduce 84%
18/10/16 09:27:48 INFO mapreduce.Job:  map 100% reduce 85%
18/10/16 09:27:51 INFO mapreduce.Job:  map 100% reduce 89%
18/10/16 09:27:54 INFO mapreduce.Job:  map 100% reduce 91%
18/10/16 09:27:57 INFO mapreduce.Job:  map 100% reduce 93%
18/10/16 09:28:00 INFO mapreduce.Job:  map 100% reduce 96%
18/10/16 09:28:03 INFO mapreduce.Job:  map 100% reduce 97%
18/10/16 09:28:06 INFO mapreduce.Job:  map 100% reduce 98%
18/10/16 09:28:09 INFO mapreduce.Job:  map 100% reduce 99%
18/10/16 09:28:11 INFO mapreduce.Job:  map 100% reduce 100%
18/10/16 09:28:11 INFO mapreduce.Job: Job job_1539675657977_0007 completed successfully
18/10/16 09:28:11 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=4477501888
                FILE: Number of bytes written=8891102479
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000047400
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=924
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=300
                Launched reduce tasks=8
                Data-local map tasks=299
                Rack-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=1406250
                Total time spent by all reduces in occupied slots (ms)=572250
                Total time spent by all map tasks (ms)=1406250
                Total time spent by all reduce tasks (ms)=572250
                Total vcore-seconds taken by all map tasks=1406250
                Total vcore-seconds taken by all reduce tasks=572250
                Total megabyte-seconds taken by all map tasks=1440000000
                Total megabyte-seconds taken by all reduce tasks=585984000
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4375223545
                Input split bytes=47400
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4375223545
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =2400
                Failed Shuffles=0
                Merged Map outputs=2400
                GC time elapsed (ms)=33681
                CPU time spent (ms)=1281580
                Physical memory (bytes) snapshot=147796410368
                Virtual memory (bytes) snapshot=853626892288
                Total committed heap usage (bytes)=155097497600
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
18/10/16 09:28:11 INFO terasort.TeraSort: done

real    6m2.391s
user    0m9.270s
sys     0m0.602s
[olgierdg@ip-172-31-46-123 ~]$
```