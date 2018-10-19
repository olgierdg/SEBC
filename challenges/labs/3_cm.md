# Command and output for hdfs dfs -ls /user

```
[hdfs@ip-172-31-16-185 ~]$ hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - fullerton fullerton          0 2018-10-19 08:26 /user/fullerton
drwxrwxrwx   - mapred    hadoop             0 2018-10-19 08:18 /user/history
drwxrwxr-t   - hive      hive               0 2018-10-19 08:19 /user/hive
drwxrwxr-x   - hue       hue                0 2018-10-19 08:20 /user/hue
drwxrwxr-x   - oozie     oozie              0 2018-10-19 08:20 /user/oozie
drwxr-xr-x   - raffles   raffles            0 2018-10-19 08:26 /user/raffles
```

# The output from the CM API call ../api/v14/hosts

```
bash-4.4$ curl -u admin:admin 'http://ec2-18-130-162-189.eu-west-2.compute.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "4013c733-1a8a-45a7-9da5-00e6139d2bd1",
    "ipAddress" : "172.31.16.185",
    "hostname" : "ip-172-31-16-185.eu-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-209.eu-west-2.compute.internal:7180/cmf/hostRedirect/4013c733-1a8a-45a7-9da5-00e6139d2bd1",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722391040
  }, {
    "hostId" : "15ba0026-eab0-40a7-862f-83c3ea224ab2",
    "ipAddress" : "172.31.17.169",
    "hostname" : "ip-172-31-17-169.eu-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-209.eu-west-2.compute.internal:7180/cmf/hostRedirect/15ba0026-eab0-40a7-862f-83c3ea224ab2",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722391040
  }, {
    "hostId" : "52f5a738-4708-4d08-8f64-4afd7ea02b79",
    "ipAddress" : "172.31.18.209",
    "hostname" : "ip-172-31-18-209.eu-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-209.eu-west-2.compute.internal:7180/cmf/hostRedirect/52f5a738-4708-4d08-8f64-4afd7ea02b79",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722391040
  }, {
    "hostId" : "837edbec-4da4-4760-9de1-1e10af17b8a9",
    "ipAddress" : "172.31.20.246",
    "hostname" : "ip-172-31-20-246.eu-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-209.eu-west-2.compute.internal:7180/cmf/hostRedirect/837edbec-4da4-4760-9de1-1e10af17b8a9",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722391040
  }, {
    "hostId" : "f478803c-28b5-44c7-b71f-dae7382b2330",
    "ipAddress" : "172.31.28.8",
    "hostname" : "ip-172-31-28-8.eu-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-209.eu-west-2.compute.internal:7180/cmf/hostRedirect/f478803c-28b5-44c7-b71f-dae7382b2330",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722391040
  } ]
}
```