# Create a precious directory in HDFS; copy the ZIP course file into it.

```
[olgierdg@ip-172-31-46-123 ~]$ hadoop fs -mkdir /user/olgierdg/precious
[olgierdg@ip-172-31-46-123 ~]$ hadoop fs -put /tmp/SEBC-master.zip /user/olgierdg/precious
[olgierdg@ip-172-31-46-123 ~]$ hadoop fs -ls /user/olgierdg/precious
Found 1 items
-rw-r--r--   3 olgierdg olgierdg    1720611 2018-10-16 09:40 /user/olgierdg/precious/SEBC-master.zip
[olgierdg@ip-172-31-46-123 ~]$
```

# Enable snapshots for precious

```
[hdfs@ip-172-31-46-123 ~]$ hdfs dfsadmin -allowSnapshot /user/olgierdg/precious
Allowing snaphot on /user/olgierdg/precious succeeded
[hdfs@ip-172-31-46-123 ~]$ 
```

# Create a snapshot called sebc-hdfs-test

```
[hdfs@ip-172-31-46-123 ~]$ hdfs dfs -createSnapshot /user/olgierdg/precious sebc-hdfs-test
Created snapshot /user/olgierdg/precious/.snapshot/sebc-hdfs-test
[hdfs@ip-172-31-46-123 ~]$
```

# Delete the directory

```
[hdfs@ip-172-31-46-123 ~]$ hadoop fs -rm -r /user/olgierdg/precious
rm: Failed to move to trash: hdfs://ip-172-31-35-238.eu-central-1.compute.internal:8020/user/olgierdg/precious: The directory /user/olgierdg/precious cannot be deleted since /user/olgierdg/precious is snapshottable and already has snapshots
[hdfs@ip-172-31-46-123 ~]$
```

# Delete the ZIP file

```
[hdfs@ip-172-31-46-123 ~]$ hadoop fs -rm /user/olgierdg/precious/SEBC-master.zip
18/10/16 09:48:56 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-35-238.eu-central-1.compute.internal:8020/user/olgierdg/precious/SEBC-master.zip' to trash at: hdfs://ip-172-31-35-238.eu-central-1.compute.internal:8020/user/hdfs/.Trash/Current/user/olgierdg/precious/SEBC-master.zip
[hdfs@ip-172-31-46-123 ~]$
```

# Restore the deleted file

```
[hdfs@ip-172-31-46-123 ~]$ hdfs dfs -cp -ptopax /user/olgierdg/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/olgierdg/precious/SEBC-master.zip
[hdfs@ip-172-31-46-123 ~]$ hadoop fs -ls /user/olgierdg/precious
Found 1 items
-rw-r--r--   3 olgierdg olgierdg    1720611 2018-10-16 09:40 /user/olgierdg/precious/SEBC-master.zip
[hdfs@ip-172-31-46-123 ~]$
```